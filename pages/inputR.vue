<template>
  <div class="container" style="margin-top: 10%">
    <form action="" @submit.prevent="($event) => addResep()">
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
                v-model="form.no_resep"
                class="form-control"
                placeholder="Username"
                aria-label="Username"
                aria-describedby="addon-wrapping"
              />
            </div>
          </div>
          <div class="mb-3 row">
            <label for="inputtext" class="col-sm-2 col-form-label"
              >Nama Dokter</label
            >
            <div class="col-sm-10">
              <input
                type="text"
                v-model="form.tgl_resep"
                class="form-control"
                placeholder="Username"
                aria-label="Username"
                aria-describedby="addon-wrapping"
              />
            </div>
          </div>
          <div class="mb-3 row">
            <label for="inputtext" class="col-sm-2 col-form-label"
              >Nama Pasien</label
            >
            <div class="col-sm-10">
              <input
                type="text"
                v-model="form.nama_pasien"
                class="form-control"
                placeholder="Username"
                aria-label="Username"
                aria-describedby="addon-wrapping"
              />
            </div>
          </div>
          <div class="input-group mb-3">
            <label for="inputtext" class="col-sm-2 col-form-label"
              >Tanggal</label
            >
            <input
              type="text"
              v-model="form.jumlah_obatresep"
              class="form-control"
              placeholder="Masukkan Tanggal"
              aria-label="Username"
            />
          </div>
          <div class="mt-3">
            <button type="button" class="btn btn-success">Tambah</button>
          </div>
        </div>
      </div>
    </form>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped></style>
