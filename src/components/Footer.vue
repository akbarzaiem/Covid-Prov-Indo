<template>
  <div class="container bottom">
    <!-- font poppins -->
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
      <p>By <a href="#">akbar zaiem</a></p>
      <p>Make it with :</p>
      <img
        class="rounded mx-auto d-block"
        src="../assets/Vue-Logo.svg"
        alt=""
      />
      <img class="rounded mx-auto d-block" src="../assets/html.svg" alt="" />
      <img class="rounded mx-auto d-block" src="../assets/css3.svg" alt="" />
      <img
        class="rounded mx-auto d-block"
        src="../assets/bootstrap-4.svg"
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
a {
  text-decoration: none;
}
</style>