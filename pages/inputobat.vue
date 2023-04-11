<template>
  <form @submit.prevent="($event) => addProduk">
    <fieldset>
      <h2>Input data Obat</h2>
      <table>
        <thead>
          <tr>
            <td>Kode Obat</td>
            <td>
              <input
                type="text"
                v-model="form.kode_obat"
                size="40"
                placeholder="kode obat"
              />
            </td>
            <td>nama Obat</td>
            <td>
              <input
                type="text"
                v-model="form.nama_obat"
                size="40"
                placeholder="nama obat"
              />
            </td>
          </tr>
          <tr>
            <td>Harga</td>
            <td>
              <input
                type="number"
                v-model="form.hargaPerUnit"
                size="40"
                placeholder="Harga"
              />
            </td>
          </tr>
          <tr>
            <td>Jumlah</td>
            <td>
              <input
                type="number"
                v-model="form.jumlah"
                size="40"
                placeholder="jumlah"
              />
            </td>
            <td>expired</td>
            <td>
              <input
                type="date"
                v-model="form.expired_date"
                size="40"
                placeholder="Expired"
              />
            </td>
          </tr>
          <tr>
            <td>photo</td>
            <td><input type="text" v-model="form.image" /></td>
            <td><button class="btn btn-primary">Tambah</button></td>
            <td><input type="button" name="batal" value="batal" /></td>
          </tr>
        </thead>
      </table>
    </fieldset>
  </form>
  <div class="container">
    <div class="row">
      <div class="card shadow mb-4">
        <div class="card-header py-3">
          <h6 class="m-0 font-weight-bold text-primary">DataTables Obat</h6>
        </div>
        <div class="card-body">
          <div class="table-responsive">
            <table
              class="table table-bordered"
              id="dataTable"
              width="100%"
              cellspacing="0"
            >
              <thead>
                <tr>
                  <th>KODE OBAT</th>
                  <th>NAMA OBAT</th>
                  <th>EXPIRED</th>
                  <th>JUMLAH</th>
                  <th>HARGA PERUNIT</th>
                  <th>GAMBARS</th>
                  <th>#</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="item in items" :key="item.id">
                  <td>{{ item.kode_obat }}</td>
                  <td>{{ item.nama_obat }}</td>
                  <td>{{ item.expired_date }}</td>
                  <td>{{ item.jumlah }}</td>
                  <td>{{ item.hargaPerUnit }}</td>
                  <td>
                    <img
                      :src="item.image"
                      class="h-100 d-inline-block"
                      style="width: 120px"
                      alt=""
                    />
                  </td>
                  <td>EDIT | DELETE</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import axios from "axios";

const form = ref({
  kode_obat: "",
  nama_obat: "",
  expired_date: "",
  jumlah: "",
  hargaPerUnit: "",
  image: "",
});

const items = ref([]);
const getData = async () => {
  const res = await axios.get("http://localhost:8000/api/produk");
  items.value = res.data;
  console.log(res.data);
};

onMounted(() => getData());

const addProduk = async () => {
  //console.log(form.value)
  const res = await axios.post("http://localhost:8000/api/produk", {
    kode_obat: form.value.kode_obat,
    nama_obat: form.value.nama_obat,
    expired_date: form.value.expired_date,
    jumlah: form.value.jumlah,
    hargaPerUnit: form.value.hargaPerUnit,
    image: form.value.image,
  });
  return res;
};
</script>

<style scoped>
input {
  margin-top: 5%;
}
form {
  padding-left: 129px;
  width: 1233px;
  font-family: math;
}
</style>
