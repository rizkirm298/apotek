<template>
  <div v-for="item in items" :key="item.id" class="card h-100 ml-4">
    <img
      :src="item.image"
      class="card-img-top"
      style="width: 100%; height: 200px"
      alt="..."
    />
    <div class="card-body">
      <h6 class="card-title">nama obat : {{ item.nama_obat }}</h6>
      <h6 class="card-title">jumlah : {{ item.jumlah }}</h6>
      <h6 class="card-title">harga : {{ item.hargaPerUnit }}</h6>
      <div class="d-grid mx-auto">
        <NuxtLink href="#" class="btn btn-secondary">PESAN SEKARANG</NuxtLink>
      </div>
    </div>
  </div>
</template>
<script setup>
import axios from "axios";
import Cardproduk from "./cardproduk.vue";
const items = ref([]);

const getData = async () => {
  const res = await axios.get("http://localhost:8000/api/produk");
  items.value = res.data;
  console.log(res.data);
};
onMounted(() => getData());
</script>

<style scoped>
.row {
  margin-top: 10%;
}
</style>
