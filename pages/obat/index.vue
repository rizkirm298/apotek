<template>
  <div>
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
  </div>
</template>

<script setup>
import axios from "axios";
import InputB from "./inputB.vue";
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
