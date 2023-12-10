<template>
  <v-footer class="bg-grey-lighten-1" style="position: fixed; bottom: 0; width: 100%;">
  <v-row justify="center" no-gutters>
      <v-btn
          v-for="link in links"
          :key="link"
          color="white"
          variant="text"
          class="mx-2"
          :rounded="false"
      >
        {{ link }}
      </v-btn>
      <v-col class="text-center mt-4" cols="12">
        {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
      </v-col>
    </v-row>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    links: [
      'O nama',
      'Uvjeti i pravila korištenja',
      'Radno vrijeme',
      'Kontakt i pomoć',
    ],
  }),
}
</script>
<style>
.v-footer {
  position: fixed;
  bottom: 0;
  width: 100%;
}
</style>