<template>
  <div class="home">
    <div class="container"><Header /> <Hero /><Footer /></div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import "bootstrap/dist/css/bootstrap.css";
import Header from "@/components/Header.vue";
import Hero from "@/components/Hero.vue";
import Footer from "@/components/Footer.vue";
export default {
  name: "Home",
  components: {
    // HelloWorld
    Header,
    Hero,
    Footer,
  },
};
</script>
