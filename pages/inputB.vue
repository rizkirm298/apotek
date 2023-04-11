<template>
  <div class="container" style="margin-top: 10%">
    <form
      @submit.prevent="($event) => addProduk()"
      class="row g-3"
      style="margin-bottom: 20%"
    >
      <div class="col-md-6">
        <label for="inputkodeobat" class="form-label">kode obat</label>
        <input
          type="text"
          v-model="form.kode_obat"
          class="form-control"
          id="inputEmail4"
        />
      </div>
      <div class="col-md-6">
        <label for="inputPassword4" class="form-label">nama obat</label>
        <input type="text" v-model="form.nama_obat" class="form-control" />
      </div>
      <div class="col-12">
        <label for="inputAddress" class="form-label">harga</label>
        <input
          type="number"
          v-model="form.hargaPerUnit"
          class="form-control"
          placeholder="masukkan harga "
        />
      </div>
      <div class="col-12">
        <label for="inputAddress2" class="form-label">jumlah 2</label>
        <input
          type="number"
          v-model="form.jumlah"
          class="form-control"
          placeholder="Apartment, studio, or floor"
        />
      </div>
      <div class="col-12">
        <label for="inputAddress2" class="form-label">expired</label>
        <input
          type="date"
          v-model="form.expired_date"
          class="form-control"
          placeholder="Apartment, studio, or floor"
        />
      </div>
      <div class="col-12">
        <label for="inputAddress2" class="form-label">gambar</label>
        <input
          type="text"
          v-model="form.image"
          class="form-control"
          placeholder="Apartment, studio, or floor"
        />
      </div>
      <div class="col-12">
        <button type="button" class="btn btn-primary">Sign in</button>
      </div>
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
                    <td>
                      <button
                        class="btn btn-danger"
                        @click="DeleteObat(item.id)"
                      >
                        delete
                      </button>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
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
const DeleteObat = async (item) => {
  const res = await axios.delete("http://localhost:8000/api/produk/" + item);
  getData();
  return res;
};
onMounted(() => getData());
</script>

<style scoped></style>
