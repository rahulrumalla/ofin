<template>
  <v-app class="grey lighten-4">
    <v-toolbar 
      fixed
      app
      flat
      class="primary--text hl">
      <span class="font-weight-bold">
        <v-icon class="primary--text">fa-leaf</v-icon>
        Ofin
        <span class="body-2">prototype</span>
      </span>
      <v-spacer />
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn 
          v-for="i in toolbarMenuItems"
          :key="i.text"
          :to="i.to"
          flat
          class="primary--text font-weight-bold tt"
          style="text-transform: none">
          {{ i.text }}
        </v-btn>
        <v-btn
          flat
          class="primary--text font-weight-bold tt"
          style="text-transform: none">
          Log Out
        </v-btn>
      </v-toolbar-items>
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
        title: 'Vuetify.js',
        toolbarMenuItems: [
          { text: 'Dashboard', to: '/' },
          { text: 'X-Change', to: '/xchange' },
          { text: 'Blend', to: '/blend' },
          { text: 'Invest', to: '/invest' },
          { text: 'Offers', to: '/offers' },
          { text: 'Anon ID', to: '/anonid' },
        ]
      }
    }
  }
</script>

<style lang="stylus">
.v-toolbar a.v-btn--active
  border-style solid;
  border-color $primary;
  border-width 0 0 4px 0;

.v-toolbar a.v-btn--active:before 
  background-color white;

</style>

