<template>
  <div>
    <!-- Start Sidebar -->
    <nav class="navbar navbar-dark bg-dark">
      <!-- navbar navbar-dark bg-dark fixed-top -->
      <div class="container-fluid">
        <a class="navbar-brand" href="#">APOTEK</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="offcanvas"
          data-bs-target="#offcanvasDarkNavbar"
          aria-controls="offcanvasDarkNavbar"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div
          class="offcanvas offcanvas-end text-bg-dark"
          tabindex="-1"
          id="offcanvasDarkNavbar"
          aria-labelledby="offcanvasDarkNavbarLabel"
        >
          <div class="offcanvas-header">
            <h5 class="offcanvas-title" id="offcanvasDarkNavbarLabel">
              Dark offcanvas
            </h5>
            <button
              type="button"
              class="btn-close btn-close-white"
              data-bs-dismiss="offcanvas"
              aria-label="Close"
            ></button>
          </div>
          <div class="offcanvas-body">
            <ul class="navbar-nav justify-content-end flex-grow-1 pe-3">
              <li class="nav-item">
                <a class="nav-link active" aria-current="page" href="#">Home</a>
              </li>
              <li class="nav-item">
                <a class="nav-link active" aria-current="page" href="#"
                  >Users</a
                >
              </li>
              <li class="nav-item">
                <a class="nav-link active" aria-current="page" href="#">Obat</a>
              </li>
              <li class="nav-item">
                <a class="nav-link active" aria-current="page" href="#"
                  >Logout</a
                >
              </li>
            </ul>
          </div>
        </div>
      </div>
    </nav>

    <div class="row" id="body-row">
      <div id="sidebar-container" class="sidebar-expanded d-none d-md-block">
        <ul class="list-group">
          <li
            class="list-group-item sidebar-separator-title text-muted d-flex align-items-center menu-collapsed"
          >
            <small>MAIN MENU</small>
          </li>
          <a
            href="#submenu1"
            data-toggle="collapse"
            aria-expanded="false"
            class="bg-dark list-group-item list-group-item-action flex-column align-items-start"
          >
            <div class="d-flex w-100 justify-content-start align-items-center">
              <span class="fa fa-dashboard fa-fw mr-3"></span>
              <span class="menu-collapsed">Home</span>
              <span class="submenu-icon ml-auto"></span>
            </div>
          </a>
          <a
            href="#submenu2"
            data-toggle="collapse"
            aria-expanded="false"
            class="bg-dark list-group-item list-group-item-action flex-column align-items-start"
          >
            <div class="d-flex w-100 justify-content-start align-items-center">
              <span class="fa fa-user fa-fw mr-3"></span>
              <span class="menu-collapsed">Users</span>
              <span class="submenu-icon ml-auto"></span>
            </div>
          </a>
          <a
            href="#submenu3"
            data-toggle="collapse"
            aria-expanded="false"
            class="bg-dark list-group-item list-group-item-action flex-column align-items-start"
          >
            <div class="d-flex w-100 justify-content-start align-items-center">
              <span class="fa fa-user fa-fw mr-3"></span>
              <span class="menu-collapsed">Obat</span>
              <span class="submenu-icon ml-auto"></span>
            </div>
          </a>
          <a
            href="#submenu4"
            data-toggle="collapse"
            aria-expanded="false"
            class="bg-dark list-group-item list-group-item-action flex-column align-items-start"
          >
            <div class="d-flex w-100 justify-content-start align-items-center">
              <span class="fa fa-user fa-fw mr-3"></span>
              <span class="menu-collapsed">Logout</span>
              <span class="submenu-icon ml-auto"></span>
            </div>
          </a>
        </ul>
      </div>
      <!-- End Sidebar -->

      <!-- MAIN -->
      <div class="col">
        <h1>ADMIN</h1>
      </div>
    </div>
  </div>
</template>

<script setup></script>

<style scoped>
#body-row {
  margin-left: 0;
  margin-right: 0;
}
#sidebar-container {
  min-height: 100vh;
  background-color: #333;
  padding: 0;
}

.sidebar-expanded {
  width: 230px;
}
.sidebar-collapsed {
  width: 60px;
}

#sidebar-container .list-group a {
  height: 50px;
  color: white;
}

#sidebar-container .list-group .sidebar-submenu a {
  height: 45px;
  padding-left: 30px;
}
.sidebar-submenu {
  font-size: 0.9rem;
}

.sidebar-separator-title {
  background-color: #333;
  height: 35px;
}
.sidebar-separator {
  background-color: #333;
  height: 25px;
}
.logo-separator {
  background-color: #333;
  height: 60px;
}

#sidebar-container
  .list-group
  .list-group-item[aria-expanded="false"]
  .submenu-icon::after {
  content: " \f0d7";
  font-family: FontAwesome;
  display: inline;
  text-align: right;
  padding-left: 10px;
}

#sidebar-container
  .list-group
  .list-group-item[aria-expanded="true"]
  .submenu-icon::after {
  content: " \f0da";
  font-family: FontAwesome;
  display: inline;
  text-align: right;
  padding-left: 10px;
}
</style>
