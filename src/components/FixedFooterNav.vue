<template>
  <nav
    class="navbar fixed-bottom navbar-dark d-block d-sm-none"
    style="background-color: #505050"
  >
    <link
      href="https://fonts.googleapis.com/css2?family=Poppins:wght@700&display=swap"
      rel="stylesheet"
    />
    <div class="navbar-brand">
      <!-- <img
          src="../assets/safety-suit.png"
          width="30"
          height="30"
          class="d-inline-block align-top"
          alt=""
        />
        Covid 19 in INDONESIA -->

      <div class="row">
        <div class="col">
          <router-link to="/indototal" class="routerlink"
            ><img src="../assets/12.png" alt="icon3" class="icon"
          /></router-link>
        </div>
        <div class="col">
          <router-link to="/about" class="routerlink"
            ><img src="../assets/12.png" alt="icon3" class="icon"
          /></router-link>
        </div>
        <div class="col">
          <router-link to="/vaccine" class="routerlink"
            ><img src="../assets/3.png" alt="icon3" class="icon"
          /></router-link>
        </div>
        <div class="w-100"></div>
        <div class="col text">
          <router-link to="/indototal" class="routerlink"
            >Data Nasional</router-link
          >
        </div>
        <div class="col text">
          <router-link to="/about" class="routerlink"
            >Data Provinsi</router-link
          >
        </div>
        <div class="col text">
          <router-link to="/vaccine" class="routerlink"
            >Data Vaksin</router-link
          >
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "FixedFoo",
};
</script>

<style scoped>
.text {
  font-size: 13px;
}
.routerlink {
  font-family: "Poppins", sans-serif;
  font-weight: 700;
  color: #27aace;
  text-decoration: none;
}
.routerlink:hover {
  color: white;
}
.icon {
  height: 30px;
  margin-bottom: -15px;
  margin-top: -18px;
}
.icon:hover {
  opacity: 0.3;
}
</style>