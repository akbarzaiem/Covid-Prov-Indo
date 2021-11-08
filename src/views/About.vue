<template>
  <div class="about">
    <div class="container">
      <Header />
      <div id="nav" class="d-none d-sm-block">
        <router-link to="/indototal" class="routerlink"
          >Data Nasional</router-link
        >
        |
        <router-link to="/about" class="routerlink">Data Provinsi</router-link>
        |
        <router-link to="/vaccine" class="routerlink">Data Vaksin</router-link>
      </div>
      <ListData class="space" />
      <Footer class="d-none d-sm-block" />
      <FixedFoo />
    </div>
  </div>
</template>

<style scoped>
#nav .routerlink {
  color: #27aace;
  text-decoration: none;
}
#nav .routerlink:hover {
  color: black;
}
.space {
  margin-bottom: 70px;
}
</style>

<script>
import "bootstrap/dist/css/bootstrap.css";
import Header from "@/components/Header.vue";
import ListData from "@/components/ListData.vue";
import Footer from "@/components/Footer.vue";
import FixedFoo from "@/components/FixedFooterNav.vue";
export default {
  name: "About",
  components: {
    Header,
    ListData,
    Footer,
    FixedFoo,
  },
};
</script>
