<template>
  <div class="container bottom">
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Poppins&display=swap"
      rel="stylesheet"
    />

    <!-- Image and text -->
    <carousel
      class="navbar navbar-light bg-light"
      :autoplay="true"
      :nav="false"
      :items="3"
      :dots="false"
      :autoplaySpeed="1"
    >
      <p>Make it with :</p>
      <img class="rounded mx-auto d-block" src="../assets/logo.png" alt="" />
      <img class="rounded mx-auto d-block" src="../assets/html.svg" alt="" />
      <img class="rounded mx-auto d-block" src="../assets/css.png" alt="" />
      <img
        class="rounded mx-auto d-block"
        src="../assets/bootstrap.png"
        alt=""
      />
    </carousel>
  </div>
</template>

<script>
import carousel from "vue-owl-carousel";
export default {
  name: "Footer",
  components: { carousel },
};
</script>

<style scoped>
.navbar img {
  margin-right: 10px;
  width: 40px;
  height: 40px;
}
.bottom {
  margin-top: 90px;
}

p {
  font-family: "Poppins", sans-serif;
  font-size: 13px;
}
</style>