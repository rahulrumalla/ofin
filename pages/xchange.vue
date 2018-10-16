<template>
  <v-container>
    <v-card
      flat
      class="mock-widget-card ma-1 primary white--text "
      style="border-radius: 5px;">
      <v-card-title
        class="hl px-3">
        Welcome to X-Change
      </v-card-title>
      <v-card-text class="tt pb-4">
        X-Change is a decentralized exchange powered by the 
        <a 
          href="https://0xproject.com" 
          target="_blank"
          style="color: inherit">
          0x Protocol
        </a>
        <div class="mt-3">
          Using X-Change you can buy, sell or trade your assets in your wallet(s).
        </div>
      </v-card-text>
    </v-card>
    <v-layout
      row
      wrap
      class="mt-2">
      <v-flex 
        md5 
        xs12
        class="pa-1">
        <aprrove-assets
          style="min-height: 420px"/>
      </v-flex>
      <v-flex 
        md7 
        xs12
        class="pa-1">
        <trade
          style="min-height: 420px"/>
      </v-flex>
    </v-layout>
    <!-- <orders /> -->
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
