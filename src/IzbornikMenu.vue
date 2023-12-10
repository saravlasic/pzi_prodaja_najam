<template>
  <v-navigation-drawer v-model="drawer" app>
    <v-list>
      <v-list-item @click="prikaziProdaju">Prodaja</v-list-item>
      <v-list-item @click="prikaziNajam">Najam</v-list-item>
      <v-list-item @click="pregledajSve">Pregledaj sve</v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  props: {
    drawer: Boolean
  },
  data() {
    return {
      drawer: false
    };
  },
  methods: {
    prikaziProdaju() {
      // Logika za prikazivanje prodaje
      console.log('Prikazuje se prodaja');
    },
    prikaziNajam() {
      // Logika za prikazivanje najma
      console.log('Prikazuje se najam');
    },
    pregledajSve() {
      // Logika za pregled svega
      console.log('Pregledaj sve');
    }
  }
};
</script>