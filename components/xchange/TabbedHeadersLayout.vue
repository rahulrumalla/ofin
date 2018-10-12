<template>
  <div>
    <v-tabs 
      class="v-tabs--transparent mt-2" 
      slider-color="primary" 
      fixed-tabs>
      <v-tab 
        :to="'/xchange/buy'"
        class="tt primary--text">
        BUY
      </v-tab>
      <v-tab 
        :to="'/xchange/sell'"
        class="tt primary--text">
        SELL
      </v-tab>
      <v-tab 
        :to="'/xchange/trade'"
        class="tt primary--text">
        TRADE
      </v-tab>
      <v-tab 
        :to="'/xchange/orders'"
        class="tt primary--text">
        YOUR ORDERS
      </v-tab>
    </v-tabs>
    <v-divider class="mx-4" />
    <v-flex>
      <slot/>
    </v-flex>
  </div>
</template>
