<template>
  <div class="about">
    <div class="container">
      <Header />
      <ListData />
      <Footer />
    </div>
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css";
import Header from "@/components/Header.vue";
import ListData from "@/components/ListData.vue";
import Footer from "@/components/Footer.vue";
export default {
  name: "About",
  components: {
    Header,
    ListData,
    Footer,
  },
};
</script>
