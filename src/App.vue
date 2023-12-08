<template>
  <v-app id="inspire">
    <v-navigation-drawer
        v-model="drawer"
        app
    >
      <!--  -->
    </v-navigation-drawer>
    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Prodaja/najam haljina</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn @click="prikaziPrijavu">Prijava</v-btn>
    </v-app-bar>
    <v-dialog v-model="dialogPrijave" max-width="500px">
      <v-card>
        <v-card-title>Prijava</v-card-title>
        <v-card-text>
          <v-form @submit.prevent="obradiPrijavu">
            <!-- Dodajte polja za unos podataka za prijavu -->
            <v-text-field v-model="korisnickoIme" label="Korisničko ime"></v-text-field>
            <v-text-field v-model="lozinka" label="Lozinka" type="password"></v-text-field>
                <v-btn type="submit">Prijavi se</v-btn>
          </v-form>
        </v-card-text>
      </v-card>
    </v-dialog>
    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      dialogPrijave: false,
      korisnickoIme: '',
      lozinka: ''
    };
  },
  methods: {
    prikaziPrijavu() {
      // Prikazivanje prijavnog prozora
      this.dialogPrijave = true;
    },
    obradiPrijavu() {
      // Implementacija logike prijave
      console.log('Podaci za prijavu:', this.korisnickoIme, this.lozinka);

      // Zatvorite prijavni prozor
      this.dialogPrijave = false;
    }
  }
};
</script>
