<template>
  <div class="container" style="margin-top: 10%">
    <form
      @submit.prevent="($event) => updateProduk()"
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
        <button type="submit" class="btn btn-primary">update</button>
      </div>
    </form>
  </div>
</template>

<script setup>
import axios from "axios";
const route = useRoute();
const form = ref({
  kode_obat: "",
  nama_obat: "",
  expired_date: "",
  jumlah: "",
  hargaPerUnit: "",
  image: "",
});
const getData = async () => {
  const res = await axios.get("http://localhost:8000/api/produk");
  const filter = res.data.filter("id" == route.params.id);
  console.log(filter);
};
const updateProduk = async () => {
  await axios.put("http://localhost:8000/api/produk/" + route.params.id + "/", {
    kode_obat: form.value.kode_obat,
    nama_obat: form.value.nama_obat,
    expired_date: form.value.expired_date,
    jumlah: form.value.jumlah,
    hargaPerUnit: form.value.hargaPerUnit,
    image: form.value.image,
  });
};
onMounted(() => {
  getData();
});
</script>
