<template>
    <div>
        <form @submit.prevent="tambahObat()">
            <fieldset align="center">
                <h2>input data obat</h2>
                <table>
                    <thead>
                        <tr>
                            <td>kode obat</td>
                            <td><input type="text" v-model="form.kode_obat" size="40" placeholder="kode obat" required></td>
                            <td>harga</td>
                            <td><input type="number" v-model="form.nama_obat" size="40" placeholder="isi nama obat"
                                    required></td>
                        </tr>
                        <tr>
                            <td>Nama produk</td>
                            <td> <input type="text" v-model="form.harga" size="40" placeholder="isi harga" required></td>
                            <td>exp</td>
                            <td><input type="date" v-model="form.expired_obat" size="40" placeholder="isi exp" required>
                            </td>
                        </tr>
                        <tr>
                            <td>stok</td>
                            <td><input type="number" v-model="form.jumlah" size="40" placeholder="isi stok" required></td>
                            <td>Photo</td>
                            <td><input type="text" v-model="form.image"></td>
                        </tr>
                        <div class="btn">
                            <td><button class="btn btn-primary">Kirim</button></td>
                            <td><button class="btn btn-primary">batal</button></td>
                        </div>
                    </thead>
                </table>
            </fieldset>
        </form>
        <br>
        <div class="main" align=" center">
            <table class="table">
                <thead class="table-info">
                    <tr>
                        <th>No</th>
                        <th>kode obat</th>
                        <th>nama obat</th>
                        <th>EXP</th>
                        <th>stok</th>
                        <th>harga</th>
                        <th>image</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="item in items" :key="item.id">
                        <td>{{ item.id }}</td>
                        <td>{{ item.kode_obat }}</td>
                        <td>{{ item.nama_obat }}</td>
                        <td>{{ item.expired_obat }}</td>
                        <td>{{ item.jumlah }}</td>
                        <td>{{ item.harga }}</td>
                        <td><img :src="assets / obat / item.image"></td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>

<script setup>
import axios from 'axios'
const form = ref({
    kode_obat: "",
    nama_obat: "",
    expired_obat: "",
    jumlah: "",
    harga: "",
    image: ""
})
const items = ref([])
const getData = async () => {
    const res = await axios.get('http://localhost:8000/api/produk')
    items.value = res.data
    console.log(res.data)
}
onMounted(() => getData())
const tambahObat = async () => {
    console.log(form.value)
    const res = await axios.post(`http://localhost:8000/api/produk`, {
        kode_obat: form.value.kode_obat,
        nama_obat: form.value.nama_obat,
        expired_obat: form.value.expired_obat,
        jumlah: form.value.jumlah,
        harga: form.value.harga,
        image: form.value.image,
    })
    return res
}
</script>

<style scoped>
input[type="text" i] {
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}
input[type="date" i] {
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}
input[type="number" i] {
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
}
.btn {
    margin-left: 10px;
}
form {
    padding-left: 129px;
    width: 1233px;
    font-family: math;
}
.main {
    width: 945px;
    height: 207px;
    margin-left: 200px;
    background: right;
}</style>
