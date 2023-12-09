<template>
  <v-app>
    <v-main class="background">
      <!-- Tvoj sadržaj ovdje -->
    </v-main>
  </v-app>

</template>
<style>
.background {
  background-image: url('/public/slike/poz.jpg'); /* Postavi putanju do slike */
  background-size: cover; /* Postavi veličinu slike */
  background-position: center center; /* Pozicioniraj sliku */
}
</style>



<script>
  //import HelloWorld from '../components/HelloWorld'

  export default {
    name: 'HomeView',


   // components: {
      //HelloWorld,
    //},
  }
</script>
