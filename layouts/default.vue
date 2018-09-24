<template>
  <v-app class="grey lighten-4">
    <v-toolbar 
      fixed
      app
      flat
      class="">
      <span class="headline primary--text font-weight-bold">
        <v-icon class="primary--text">fa-leaf</v-icon>
        Ofin
      </span>
    </v-toolbar>
    <v-content>
      <nuxt />
    </v-content>
  </v-app>
</template>

<script>
  export default {
    data() {
      return {
        clipped: false,
        title: 'Vuetify.js'
      }
    }
  }
</script>
