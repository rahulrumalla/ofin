<template>
  <div>
    <v-tabs 
      class="v-tabs--transparent mt-2" 
      slider-color="primary" 
      fixed-tabs>
      <v-tab 
        :to="'/xchange'"
        class="tt primary--text">
        TRADE
      </v-tab>
      <v-tab 
        :to="'/xchange/orders'"
        class="tt primary--text">
        YOUR ORDERS
      </v-tab>
    </v-tabs>
    <v-flex>
      <slot/>
    </v-flex>
  </div>
</template>
