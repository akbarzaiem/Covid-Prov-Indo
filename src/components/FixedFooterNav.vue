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

        <!-- <div class="w-100"></div>
          <div class="col">col 4</div>
          <div class="col">col 5</div>
          <div class="col">col 6</div> -->
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
  font-size: 12px;
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
</style>