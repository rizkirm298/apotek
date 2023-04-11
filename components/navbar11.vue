<template>
  <div>
    <nav
      class="navbar navbar-expand-lg bg-body-dark"
      style="background-color: darkgrey"
    >
      <div class="container-fluid">
        <NuxtLink class="navbar-brand" to="#">APOTEK</NuxtLink>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav mx-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <NuxtLink class="nav-link active mx-4" aria-current="page" to="/"
                >Home</NuxtLink
              >
            </li>
            <li class="nav-item">
              <NuxtLink
                class="nav-link active mx-4"
                aria-current="page"
                to="/obat"
                >Obat</NuxtLink
              >
            </li>
            <li class="nav-item">
              <NuxtLink
                class="nav-link active mx-4"
                aria-current="page"
                to="/resep"
                >Resep</NuxtLink
              >
            </li>
          </ul>
          <form class="d-flex" role="search">
            <input
              class="form-control me-2"
              type="search"
              placeholder="Search"
              aria-label="Search"
            />
            <button class="btn btn-secondary mr-4" type="submit">Search</button>
          </form>
          <NuxtLink to="/login"
            ><button type="button" class="btn btn-primary">
              login
            </button></NuxtLink
          >
        </div>
      </div>
    </nav>
  </div>
</template>

<style scoped>
ul {
  cursor: pointer;
}
</style>
