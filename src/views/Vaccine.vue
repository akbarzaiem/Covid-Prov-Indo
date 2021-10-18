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
        <div
          class="
            col
            align-self-center
            col-xl-6 col-lg-6 col-md-6 col-sm-12 col-12
          "
        >
          <div class="image d-none d-sm-block">
            <img src="../assets/vaccine.jpg" alt="vaccine image" />
            <p class="attribute d-none d-sm-block">
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
        <div class="dua col align-self-center">
          <h3 class="tittle">Jumlah Penerima Vaksin di Indonesia</h3>
          <p class="tittle-vak">Vaksinasi 1</p>
          <p class="percent">{{ percentVaksin1 }} %</p>
          <span class="result">
            {{ vaksin.vaksinasi1 }}
          </span>
          <span class="from">dari </span>
          <span class="result">{{ vaksin.totalsasaran }}</span>
          <span class="from"> penerima vaksin </span>
          <p class="tittle-vak">Vaksinasi 2</p>
          <p class="percent">{{ percentVaksin2 }} %</p>
          <span class="result">
            {{ vaksin.vaksinasi2 }}
          </span>
          <span class="from">dari </span>
          <span class="result">{{ vaksin.totalsasaran }}</span>
          <span class="from"> penerima vaksin </span>
          <p class="update">Last Update : {{ vaksin.lastUpdate }}</p>
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

  computed: {
    totalVaksin1() {
      return this.vaksin.vaksinasi1;
    },
    totalVaksin2() {
      return this.vaksin.vaksinasi2;
    },
    totalKeseluruhanData() {
      return this.vaksin.totalsasaran;
    },
    percentVaksin1() {
      return ((this.totalVaksin1 / this.totalKeseluruhanData) * 100).toFixed(2);
    },
    percentVaksin2() {
      return ((this.totalVaksin2 / this.totalKeseluruhanData) * 100).toFixed(2);
    },
  },
};
</script>

<style scoped>
.vaksin {
  margin-top: 25px;
}
.image img {
  width: 290px;
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
  font-size: 20px;
  font-family: "Graduate", cursive;
}
.from {
  font-family: "Poppins", sans-serif;
}
.attribute {
  color: black;
  font-size: 8px;
}
.percent {
  font-size: 40px;
  font-family: "Graduate", cursive;
}
.update {
  margin-top: 30px;
  font-family: "Poppins", sans-serif;
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
/* Small devices (landscape phones, 576px and up) */
@media (min-width: 300px) and (max-width: 576px) {
  .dua {
    background-image: url("../assets/vaccine sm.jpg");
    background-repeat: no-repeat;
    background-position: 50%;
    background-size: cover;
    border-radius: 20px;
    margin: 0 15px 0 15px;
  }
}
</style>