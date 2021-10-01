<template>
  <div class="container">
    <Header />
    <div class="total">
      <p>Positif {{ total.positif }}</p>
      <p>Meninggal {{ total.meninggal }}</p>
      <p>Sembuh {{ total.sembuh }}</p>
      <p>Dirawat {{ total.dirawat }}</p>
      <p>Update {{ total.lastUpdate }}</p>
    </div>
    <Footer />
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css";
import axios from "axios";
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
export default {
  name: "IndoTotal",
  components: { Header, Footer },
  data() {
    return {
      total: [],
    };
  },
  mounted() {
    axios
      .get("https://apicovid19indonesia-v2.vercel.app/api/indonesia")
      .then((response) => (this.total = response.data));
  },
};
</script>