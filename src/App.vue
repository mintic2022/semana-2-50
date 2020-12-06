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
            <b-nav-item href="#equipo">Equipo</b-nav-item>
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

    <!-- Seccion de Integrantes -->
    <div class="row justify-content-md-center mt-5" id=equipo>
      <h1>Equipo</h1>
    </div>
    <div class="container-fluid">
      <div class="row justify-content-center mt-1 mb-2">
        <div class="card-group">
          <div class="col mt-3" v-for="(item, index) of member" :key="index">
            <team-card v-bind:member="item"></team-card>
          </div>
        </div>
      </div>
    </div>
    <!-- FIN de Integrantes -->    

    <PageFooter />
  </div>
</template>

<script>
import News from './components/News.vue';
import PageFooter from './components/PageFooter.vue';
import Carousel from './components/Carousel.vue';
import TeamCard from './components/TeamCard.vue';

export default {
  name: 'App',
  components: {
    News,
    PageFooter,
    Carousel,
    TeamCard
  },

data(){
  return{
    member: [
      {
        codigo : 1214734035 ,
        nombre : 'Jefferson Andrés Espejo Goez' ,
        descripcion : 'Ingeniero electricista en formación en la UN sede Medellín. Pasatiempos el tenis de campo y la programación. Me gusta leer novelas en mis ratos libres y tomar mucho café' ,
        rol : 'Desarrollador Frontend' ,
        image : require('../src/assets/images/foto1.png')
      },
      {
        codigo : 1035426930 ,
        nombre : 'Jose Luis Muñoz' ,
        descripcion : 'Futuro Programador Full Stack de la UTP. 28 años. Como pasatiempo me gustar hacer deporte y escuchar musica' ,
        rol : 'Arquitecto de Software' ,
        image : require('../src/assets/images/foto2.png')
      },
      {
        codigo : 16915663 ,
        nombre : 'Fabián Díaz' ,
        descripcion : '39 años,Ingeniero Telematico - Master en Direccion de Comercio Internacional con 39 años. Pasatiempos: Buceo, Paracaidismo, Trail Running, Criptoactivos y Blockchain' ,
        rol : 'Desarrollador Backend' ,
        image : require('../src/assets/images/foto3.png')
      },
      {
        codigo : 1032370645 ,
        nombre : 'Néstor Manosalva Barrera' ,
        descripcion : 'Ingeniero de Sistemas de la UNAL de Bogotá con 34 años. Pasatiempos: camping, fotografía, drones' ,
        rol : 'Analista de Software' ,
        image : require('../src/assets/images/foto4.png')
      },
      {
        codigo : 1093787178 ,
        nombre : 'Freyberth Pabón' ,
        descripcion : 'Ingeniero Electromecanico graduado de la UFPS con 24 años. Pasatiempos: Me gustan los videojuegos y hacer deporte' ,
        rol : 'Tester' ,
        image : require('../src/assets/images/foto5.png')
      }
    ]
  }
}
};

</script>

<style scoped>
.card {
  margin: 0 auto; /* Added */
  float: none; /* Added */
  margin-bottom: 10px; /* Added */
}
</style>
