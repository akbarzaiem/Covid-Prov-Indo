<template>
  <div class="container">
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Poppins:wght@700&display=swap"
      rel="stylesheet"
    />
    <div class="sourceData text-left">
      <p>
        Data from :
        <a>Kemenkes RI</a>
      </p>
    </div>

    <div class="row" v-if="info.length > 0">
      <div
        v-for="covid in info"
        :key="covid.provinsi"
        class="card col-xl-3 col-lg-3 col-sm-6 col-12 covid"
        style="width: 18rem"
      >
        <div class="card-body">
          <h4 class="card-title">{{ covid.provinsi }}</h4>
          <div class="card-text">
            <p>Positif :{{ covid.kasus }} jiwa</p>
            <p>Dirawat :{{ covid.dirawat }} jiwa</p>
            <p>Sembuh :{{ covid.sembuh }} jiwa</p>
            <p>Meninggal :{{ covid.meninggal }} jiwa</p>
          </div>
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
</template>

<script>
import axios from "axios";
export default {
  name: "ListData",
  data() {
    return {
      info: [],
    };
  },

  mounted() {
    axios
      .get("https://apicovid19indonesia-v2.vercel.app/api/indonesia/provinsi")
      .then((response) => (this.info = response.data));
  },
};
</script>

<style scoped>
.container {
  margin-top: 40px;
}

h4 {
  font-family: "Poppins", sans-serif;
}
.sourceData a {
  text-decoration: none;
}
.sourceData {
  font-size: 13px;
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