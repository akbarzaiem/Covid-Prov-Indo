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
      <router-link to="/">Home</router-link> |
      <router-link to="/indototal">Data Nasional</router-link> |
      <router-link to="/about">Data Provinsi</router-link> |
      <router-link to="/vaccine">Data Vaksin</router-link>
    </div>
    <div class="vaksin" v-if="vaksin.length !== 0">
      <div class="row">
        <div class="col align-self-center">
          <div class="image">
            <img src="../assets/vaccine.jpg" alt="vaccine image" />
            <p class="attribute">
              Photo by
              <a
                href="https://unsplash.com/@schluditsch?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText"
                >Daniel Schludi</a
              >
              on
              <a
                href="https://unsplash.com/?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText"
                >Unsplash</a
              >
            </p>
          </div>
        </div>
        <div class="col align-self-center">
          <h3 class="tittle">Jumlah Penerima Vaksin di Indonesia</h3>
          <p class="tittle-vak">Vaksinasi 1</p>
          <span class="result">
            {{ vaksin.vaksinasi1 }}
          </span>
          <span class="from">dari </span>
          <span>{{ vaksin.totalsasaran }}</span>
          <p class="tittle-vak">Vaksinasi 2</p>
          <span class="result">
            {{ vaksin.vaksinasi2 }}
          </span>
          <span class="from">dari </span>
          <span>{{ vaksin.totalsasaran }}</span>
        </div>
      </div>
    </div>
    <div class="row" v-else>
      <div class="col-lg-12">
        <div class="loader mx-auto d-block"></div>
        <p style="margin-top: 10px">Loading....</p>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css";
import Header from "@/components/Header.vue";
import Footer from "@/components/Footer.vue";
import axios from "axios";
export default {
  name: "Vaccine",
  components: {
    Header,
    Footer,
  },
  data() {
    return {
      vaksin: [],
    };
  },

  mounted() {
    axios
      .get("https://vaksincovid19-api.vercel.app/api/vaksin")
      .then((response) => (this.vaksin = response.data));
  },
};
</script>

<style scoped>
.vaksin {
  margin-top: 40px;
}
.image img {
  width: 300px;
  border-radius: 20px;
}
.tittle {
  font-family: "Poppins", sans-serif;
}
.vaksin .tittle-vak {
  font-family: "Poppins", sans-serif;
  font-size: 20px;
  margin-top: 40px;
}
.result {
  font-size: 40px;
  font-family: "Graduate", cursive;
}
.from {
  font-family: "Poppins", sans-serif;
}
.attribute {
  color: black;
  font-size: 8px;
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