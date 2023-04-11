<template>
  <div>
    <nav class="navbar navbar-expand-lg bg-secondary">
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
              <NuxtLink class="nav-link active" aria-current="page" to="/obat"
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
    <input type="checkbox" id="check" />
    <div class="bg-secondary sidebar">
      <div class="profile_info">
        <h4>APOEK</h4>
      </div>
      <a href="#"><i class="fas fa-desktop"></i><span>Dashboard</span></a>
      <a href="#"><i class="fas fa-cogs"></i><span>Components</span></a>
      <a href="#"><i class="fas fa-table"></i><span>Tables</span></a>
      <a href="#"><i class="fas fa-th"></i><span>Forms</span></a>
      <a href="#"><i class="fas fa-info-circle"></i><span>About</span></a>
      <a href="#"><i class="fas fa-sliders-h"></i><span>Settings</span></a>
    </div>
  </div>
</template>

<script setup></script>

<style scoped>
body {
  margin: 0;
  padding: 0;
  font-family: "Roboto", sans-serif;
}

.sidebar {
  z-index: 1;
  top: 0;
  margin-top: 0px;
  padding-top: 30px;
  position: fixed;
  left: 0;
  width: 250px;
  height: calc(100% - 9%);
  transition: 0.5s;
  transition-property: left;
  overflow-y: auto;
}

.profile_info {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.sidebar .profile_info .profile_image {
  width: 100px;
  height: 100px;
  border-radius: 100px;
  margin-bottom: 10px;
}

.sidebar .profile_info h4 {
  color: #ccc;
  margin-top: 0;
  margin-bottom: 20px;
}

.sidebar a {
  color: #fff;
  display: block;
  width: 100%;
  line-height: 60px;
  text-decoration: none;
  padding-left: 40px;
  box-sizing: border-box;
  transition: 0.5s;
  transition-property: background;
}

.sidebar a:hover {
  background: #19b3d3;
}

.sidebar i {
  padding-right: 10px;
}

label #sidebar_btn {
  z-index: 1;
  color: #fff;
  position: fixed;
  cursor: pointer;
  left: 300px;
  font-size: 20px;
  margin: 5px 0;
  transition: 0.5s;
  transition-property: color;
}

label #sidebar_btn:hover {
  color: #19b3d3;
}

#check:checked ~ .sidebar {
  left: -185px;
}

#check:checked ~ .sidebar a span {
  display: none;
}

#check:checked ~ .sidebar a {
  font-size: 20px;
  margin-left: 165px;
  width: 100%;
}

@media screen and (max-width: 780px) {
  .sidebar {
    display: none;
  }

  #sidebar_btn {
    display: none;
  }

  .content {
    margin-left: 0;
    margin-top: 0;
    padding: 10px 20px;
    transition: 0s;
  }

  #check:checked ~ .content {
    margin-left: 0;
  }
}
</style>
