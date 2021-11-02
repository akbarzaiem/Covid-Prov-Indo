<template>
  <div class="container">
    <!-- font graduate -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Graduate&display=swap"
      rel="stylesheet"
    />
    <!-- font poppins -->
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Poppins:wght@500&display=swap"
      rel="stylesheet"
    />
    <Header />
    <div id="nav">
      <router-link to="/indototal">Data Nasional</router-link> |
      <router-link to="/about">Data Provinsi</router-link> |
      <router-link to="/vaccine">Data Vaksin</router-link>
    </div>
    <div class="hasil">
      <p class="top-tittle">Jumlah Kasus Covid 19 di Indonesia</p>
      <div class="row" v-if="total.length !== 0">
        <div class="col-lg-6" style="margin-bottom: 30px">
          <p class="tittle">Positif</p>
          <span class="data">{{ total.positif }}</span>
          <span> terkonfirmasi</span>
        </div>
        <div class="col-lg-6" style="margin-bottom: 30px">
          <p class="tittle">Sembuh</p>
          <span class="data">{{ total.sembuh }}</span>
          <span> jiwa</span>
        </div>
        <div class="col-lg-6" style="margin-bottom: 30px">
          <p class="tittle">Dirawat</p>
          <span class="data">{{ total.dirawat }}</span>
          <span> jiwa</span>
        </div>
        <div class="col-lg-6" style="margin-bottom: 30px">
          <p class="tittle">Meninggal</p>
          <span class="data">{{ total.meninggal }}</span>
          <span> jiwa</span>
        </div>

        <div class="col-lg-12">
          <div class="update">
            <p class="tittle">Last Update</p>
            <p>{{ total.lastUpdate }}</p>
          </div>
        </div>
      </div>
      <div class="row" v-else>
        <div class="col-lg-12">
          <div class="loader mx-auto d-block"></div>
          <p style="margin-top: 10px">Loading....</p>
        </div>
      </div>
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

<style scoped>
.hasil {
  margin-top: 25px;
}
.data {
  font-size: 50px;
  font-family: "Graduate", cursive;
}
.tittle {
  font-size: 20px;
  font-family: "Poppins", sans-serif;
}
.update {
  font-size: 13px;
}
.top-tittle {
  font-size: 30px;
  margin-bottom: 30px;
}
.loader {
  border: 15px solid #f3f3f3;
  border-radius: 50%;
  border-top: 16px solid #3498db;
  width: 80px;
  height: 80px;
  -webkit-animation: spin 2s linear infinite; /* Safari */
  animation: spin 2s linear infinite;
}
@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>