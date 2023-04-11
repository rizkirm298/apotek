<template>
  <div>
    <nav class="navbar navbar-expand-lg fixed-top bg-secondary">
      <div class="container-fluid">
        <NuxtLink class="navbar-brand" to="#">Navbar</NuxtLink>
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
              <NuxtLink class="nav-link active" aria-current="page" to="/awal"
                >kelola user</NuxtLink
              >
            </li>
            <li class="nav-item">
              <NuxtLink class="nav-link active" aria-current="page" to="/inputB"
                >obat</NuxtLink
              >
            </li>

            <!-- <li class="nav-item dropdown">
              <a
                class="nav-link dropdown-toggle"
                href="#"
                role="button"
                data-bs-toggle="dropdown"
                aria-expanded="false"
              >
                Obat
              </a>
              <ul class="dropdown-menu">
                <li><a class="dropdown-item" href="#">Action</a></li>
                <li><a class="dropdown-item" href="#">Another action</a></li>
                <li><hr class="dropdown-divider" /></li>
                <li>
                  <a class="dropdown-item" href="#">Something else here</a>
                </li>
              </ul>
            </li> -->
            <li class="nav-item">
              <NuxtLink class="nav-link active" aria-current="page" to="/resep"
                >resep</NuxtLink
              >
            </li>
            <li class="nav-item">
              <NuxtLink
                to="login"
                class="nav-link active"
                aria-current="page"
                href="#"
                ><button
                  type="button"
                  class="btn btn-success"
                  style="
                    --bs-btn-padding-y: 0.25rem;
                    --bs-btn-padding-x: 0.5rem;
                    --bs-btn-font-size: 0.75rem;
                  "
                >
                  Login
                </button></NuxtLink
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
            <button class="btn btn-outline-dark" type="submit">Search</button>
          </form>
        </div>
      </div>
    </nav>
  </div>
</template>

<script setup></script>

<style scoped></style>
