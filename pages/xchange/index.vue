<template>
  <v-container>
    <v-card
      flat
      class="white"
      style="border-radius: 5px;">
      <v-card-title
        class="primary--text d1 px-3">
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
    <tabbed-headers-layout />
  </v-container>
</template>

<script>
import TabbedHeadersLayout from '~/components/xchange/TabbedHeadersLayout'

export default {
  components: {
    TabbedHeadersLayout
  }
}
</script>
