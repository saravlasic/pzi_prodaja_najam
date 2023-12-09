<template>
  <v-app id="inspire">
    <v-navigation-drawer
        v-model="drawer"
        app
    >
      <!--  -->
      <v-tabs v-model="activeTab" slider-color="primary">
        <v-tab v-for="(item, index) in tabs" :key="index" @click="activeTab = index">
          {{ item }}
        </v-tab>
      </v-tabs>
    </v-navigation-drawer>
    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Prodaja/najam haljina</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn @click="prikaziPrijavu">Prijava</v-btn>
    </v-app-bar>
    <v-dialog v-model="dialogPrijave" max-width="500px">
      <v-card>
        <v-card-title v-if="!registracijaMode">Prijava</v-card-title>
        <v-card-title v-else>Registracija</v-card-title>
        <v-card-text>
          <v-form v-if="!registracijaMode" @submit.prevent="obradiPrijavu">
            <!-- Dodajte polja za unos podataka za prijavu -->
            <v-text-field v-model="korisnickoIme" label="Korisničko ime"></v-text-field>
            <v-text-field v-model="lozinka" label="Lozinka" type="password"></v-text-field>
            <p style="font-size: 0.8em; margin-top: 8px;">
              Potreban vam je račun? <a href="#" @click="prikaziRegistraciju">Registrirajte se</a>
            </p>
            <v-btn type="submit">Prijavi se</v-btn>
          </v-form>
          <v-form v-else @submit.prevent="obradiRegistraciju">
            <!-- Dodajte polja za registraciju -->
            <v-text-field v-model="ime" label="Ime"></v-text-field>
            <v-text-field v-model="prezime" label="Prezime"></v-text-field>
            <v-text-field v-model="brojTelefona" label="Broj telefona"></v-text-field>
            <v-text-field v-model="email" label="Email"></v-text-field>
            <v-text-field v-model="novaLozinka" label=" Lozinka" type="password"></v-text-field>
            <v-btn type="submit">Registrirajte se</v-btn>
            <p style="font-size: 0.8em; margin-top: 8px;">
              Već imate račun? <a href="#" @click="prikaziPrijavu">Prijavite se</a>
            </p>
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
      lozinka: '',
      ime: '',
      prezime: '',
      brojTelefona: '',
      email: '',
      novaLozinka: '',
      drawer: false,
      tabs: ['Prodaja','Najam'],
      activeTab: null,
      registracijaMode: false
    };
  },
  methods: {
    prikaziPrijavu() {
      this.dialogPrijave = true;
      this.registracijaMode = false;
    },
    prikaziRegistraciju() {
      this.registracijaMode = true;
      this.dialogPrijave = true;
    },
    obradiPrijavu() {
      console.log('Podaci za prijavu:', this.korisnickoIme, this.lozinka);
      this.dialogPrijave = false;
    },
    obradiRegistraciju() {
      console.log('Podaci za registraciju:', this.ime, this.prezime, this.brojTelefona, this.email, this.novaLozinka);
      this.dialogPrijave = false;
    }
  }
};
</script>