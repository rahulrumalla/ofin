<template>
  <v-card 
    flat
    class="mock-widget-card primary--text">
    <v-card-title>
      <v-layout row>
        <v-flex
          xs8 
          class="d1">
          Overall Balance
        </v-flex>
        <v-flex 
          xs4
          class="text-xs-right">
          <v-btn
            icon
            dark
            class="ma-0">
            <v-icon medium>fa-cog</v-icon>
          </v-btn>
        </v-flex>
      </v-layout>
    </v-card-title>
    <v-card-text>
      <div 
        class="d1">
        34,500.04
        <sup 
          class="tt">
          USD
        </sup>
      </div>
      <div 
        class="hl blue--text text--accent-1">
        1,700.093
        <sup 
          class="subheading">
          ETH
        </sup>
      </div>
    </v-card-text>
  </v-card>
</template>
