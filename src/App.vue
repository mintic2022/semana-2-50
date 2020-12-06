<template>
  <div id="app">
    <b-navbar toggleable="lg" type="dark" variant="info">
      <b-container>
        <b-navbar-brand href="#">Equipo 50</b-navbar-brand>
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item href="#">Inicio</b-nav-item>
            <b-nav-item href="#news">Noticias</b-nav-item>
            <b-nav-item href="#">Equipo</b-nav-item>
          </b-navbar-nav>
        </b-collapse>
      </b-container>
    </b-navbar>
    <b-container fluid id="Carousel">
      <Carousel />
    </b-container>
    <b-container fluid id="news">
      <b-row class="mt-5 text-center justify-content-md-center">
        <h1>Noticias</h1>
      </b-row>
      <News />
    </b-container>
    <PageFooter />
  </div>
</template>

<script>
import News from './components/News.vue';
import PageFooter from './components/PageFooter.vue';
import Carousel from './components/Carousel.vue';
export default {
  name: 'App',
  components: {
    News,
    PageFooter,
    Carousel,
  },
};
</script>

<style scoped>
.card {
  margin: 0 auto; /* Added */
  float: none; /* Added */
  margin-bottom: 10px; /* Added */
}
</style>
