<template>
  <v-container>
    <v-card
      flat
      class="mock-widget-card ma-1 primary white--text "
      style="border-radius: 5px;">
      <v-card-title
        class="hl px-3">
        Welcome to Blend
      </v-card-title>
      <v-card-text class="tt pb-4">
        Blend allows you to borrow and lend your cryptoassets, powered by the 
        <a 
          href="https://dharma.io" 
          target="_blank"
          style="color: inherit">
          Dharma Protocol
        </a>
        <div class="mt-3">
          Using Blend, you can participate in the open financial system in a decentralized manner.
        </div>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script>
import Trade from '~/components/xchange/Trade'
import AprroveAssets from '~/components/xchange/ApproveAssets'
import Orders from '~/components/xchange/Orders'

export default {
  components: {
    Trade,
    AprroveAssets,
    Orders
  }
}
</script>
