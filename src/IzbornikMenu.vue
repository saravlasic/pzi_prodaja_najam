<template>
  <v-navigation-drawer v-model="localDrawer" app>
    <v-list>
      <v-list-item @click="prikaziProdaju">Prodaja</v-list-item>
      <v-divider></v-divider>
      <v-list-item @click="prikaziNajam">Najam</v-list-item>
      <v-divider></v-divider>
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
      localDrawer: false
    };
  },
  watch: {
    drawer(newValue) {
      this.localDrawer = newValue;
    }
  },
  methods: {
    prikaziProdaju() {
      console.log('Prikazuje se prodaja');
    },
    prikaziNajam() {
      console.log('Prikazuje se najam');
    },
    pregledajSve() {
      console.log('Pregledaj sve');
    },
    toggleDrawer() {
      this.localDrawer = !this.localDrawer;
      this.$emit('update:drawer', this.localDrawer);
    }
  }
};
</script>