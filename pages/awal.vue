<template>
  <div class="container">
    <div class="row row-cols-1 mt-5 row-cols-md-5 g-5">
      <Cardproduk />
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
