<template>
  <div>
    <InputR />
    <div class="container">
      <div class="row">
        <div class="card shadow mb-4">
          <div class="card-header py-3">
            <h6 class="m-0 font-weight-bold text-primary">DataTables Reseo</h6>
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
                    <th>NO RESEP</th>
                    <th>TGL RESEP</th>
                    <th>NAMA PASIEN</th>
                    <th>NAMA DOKTER</th>
                    <th>OBAT RESEP</th>
                    <th>JUMLAH</th>
                    <th>#</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="item in items" :key="item.id">
                    <!-- <td>{{ item.id }}</td> -->
                    <td>{{ item.no_resep }}</td>
                    <td>{{ item.tgl_resep }}</td>
                    <td>{{ item.nama_pasien }}</td>
                    <td>{{ item.nama_dokter }}</td>
                    <td>{{ item.obat_resep }}</td>
                    <td>{{ item.jumlah_obatresep }}</td>
                    <td>Edit | Delete</td>
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
import InputR from "./inputR.vue";
const items = ref([]);

const getData = async () => {
  const res = await axios.get("http://localhost:8000/api/resep");
  items.value = res.data;
};
onMounted(() => getData());
</script>

<style scoped>
.row {
  margin-top: 10%;
}
</style>
