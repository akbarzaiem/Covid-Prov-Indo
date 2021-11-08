<template>
  <div class="container">
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Poppins:wght@700&display=swap"
      rel="stylesheet"
    />
    <div class="row">
      <div
        class="
          satu
          col-xl-6 col-lg-6 col-md-6 col-sm-12 col-12
          align-self-center
        "
      >
        <div class="tittle">
          <p>Covid 19 di Indonesia</p>
        </div>
        <div class="keterangan text-justify">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus
          pariatur dignissimos doloribus earum esse dolorem laudantium,
          quibusdam cupiditate quia magni ratione, repellat obcaecati illo
          minus. Possimus magni quaerat voluptas facere.
        </div>
        <div class="button-hero">
          <router-link style="text-decoration: none" to="/indototal">
            <button type="button" class="btn btn-primary btn-lg">
              <p>Lihat Data</p>
            </button>
          </router-link>
        </div>
      </div>
      <div
        class="col-xl-6 col-lg-6 col-md-6 col-sm-12 col-12 align-self-center"
      >
        <div class="image-hero">
          <a href="https://www.freepik.com/photos/woman">
            <img
              src="../assets/hero.webp"
              alt="hero image"
              class="d-none d-sm-block"
            />
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Hero",
};
</script>

<style scoped>
.container {
  margin-top: 50px;
}
.tittle p {
  font-family: "Poppins", sans-serif;
  font-size: 45px;
}
.button-hero button {
  border-radius: 30px;
  margin-top: 20px;
  height: 50px;
}
.button-hero p {
  color: white;
}
.image-hero img {
  width: 530px;
  border-radius: 15px;
}

/* Small devices (landscape phones, 576px and up) */
@media (min-width: 300px) and (max-width: 576px) {
  .satu {
    background-image: url("../assets/hero sm.webp");
    background-repeat: no-repeat;
    background-position: 50%;
    background-size: cover;
    border-radius: 20px;
  }

  .button-hero {
    margin-top: 20px;
    margin-bottom: 20px;
  }
  .image-hero img,
  a {
    width: 300px;
  }
}

/* Medium devices (tablets, 768px and up) */
@media (min-width: 577px) and (max-width: 768px) {
  .button-hero {
    margin-top: 20px;
    margin-bottom: 20px;
  }
  .image-hero img {
    width: 320px;
    border-radius: 15px;
  }
}

/* Medium devices (tablets, less than 992px) */
@media (min-width: 769px) and (max-width: 1023px) {
  .button-hero {
    margin-top: 20px;
    margin-bottom: 20px;
    display: flex;
    justify-content: left;
    align-items: left;
  }
  .image-hero img {
    width: 310px;
    border-radius: 15px;
  }
  .tittle p {
    font-family: "Poppins", sans-serif;
    font-size: 40px;
  }
}

/* Extra large devices (large desktops, 1200px and up) */
@media (min-width: 1024px) and (max-width: 1200px) {
  .button-hero {
    margin-top: 20px;
    margin-bottom: 20px;
    display: flex;
    justify-content: left;
    align-items: left;
  }
  .image-hero img {
    width: 440px;
    border-radius: 15px;
  }
}
/* Extra large devices (large desktops, 1200px and up) */
@media (min-width: 1201px) {
  .button-hero {
    margin-top: 20px;
    margin-bottom: 20px;
    display: flex;
    justify-content: left;
    align-items: left;
  }
}
</style>