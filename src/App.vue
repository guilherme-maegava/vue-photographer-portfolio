<template>
  <v-app>
    <v-toolbar dense dark tab  height="30px">
      <!-- <v-spacer></v-spacer>
      <v-toolbar-items>
        <v-btn flat>Home</v-btn>
        <v-btn flat>Trabalhos</v-btn>
        <v-btn flat>Sobre</v-btn>
        <v-btn flat>Contato</v-btn>
      </v-toolbar-items> -->
      <v-tabs centered slider-color="white" show-arrows height="30px">
        <v-tab>
          <v-btn small flat to="/">Home</v-btn>
        </v-tab>
        <v-tab>
          <v-btn small flat to="/portfolio">Trabalhos</v-btn>
        </v-tab>
        <v-tab>
           <v-btn small flat>Sobre</v-btn>
        </v-tab>
        <v-tab>
          <v-btn small flat to="/contact">Contato</v-btn>
        </v-tab>
      </v-tabs>
    </v-toolbar>
    <v-container fluid px-0 py-0>
      <router-view/>
    </v-container>
    <v-footer>
      <v-spacer></v-spacer>
      <span>Desenvolvido por Guilherme Maegava &copy; {{new Date().getFullYear()}}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: true,
      fixed: false,
      items: [{
        icon: 'bubble_chart',
        title: 'Inspire'
      }],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Caio Brum'
    }
  },
  name: 'App'
}
</script>
