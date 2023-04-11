<template>
  <div class="container" style="margin-top: 10%">
    <div class="card mt-5 w-90 mb-3">
      <div class="card-header text-center">KELOLA RESEP</div>
      <div class="card-body">
        <div class="mb-3 row">
          <label for="inputtext" class="col-sm-2 col-form-label"
            >No Resep</label
          >
          <div class="col-sm-10">
            <input
              type="text"
              class="form-control"
              placeholder="Username"
              aria-label="Username"
              aria-describedby="addon-wrapping"
            />
          </div>
        </div>
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
        <div class="mt-3">
          <button type="button" class="btn btn-success">Tambah</button>
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

<style lang="scss" scoped></style>
