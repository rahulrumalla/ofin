<template>
  <v-card 
    flat
    class="white primary--text"
    style="border-radius: 5px;">
    <v-card-title 
      class="pb-0">
      <v-layout row>
        <v-flex 
          xs8
          class="d1">
          Assets
        </v-flex>
        <v-flex 
          xs4
          class="text-xs-right">
          <v-btn
            icon
            class="ma-0 primary--text">
            <v-icon medium>pie_chart</v-icon>
          </v-btn>
        </v-flex>
      </v-layout>
    </v-card-title>
    <v-card-text>
      <v-layout 
        v-for="a in assets"
        :key="a.Address"
        row
        class="my-4 pb-2">
        <v-flex 
          xs6
          class="">
          <div class="tt">{{ a.Name }}</div>
        </v-flex>
        <v-flex 
          xs6
          class="text-xs-right">
          <div class="tt black--text">
            {{ a.Balance }} {{ a.Name }}
          </div>
          <div class="grey--text subheading mt-2">{{ a.Balance }} USD</div>
        </v-flex>
      </v-layout>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  data () {
    return {
      assets: [
        { Name: 'ETH', Balance: 13.295, Address: '0xh234....1233', ImageURI: 'https://manager.balance.io/static/media/eth.5e8d1d90.svg' },
        { Name: 'DAI', Balance: 2399.44, Address: 'mydaiwallet.ens', ImageURI: '' },
        { Name: 'BTC', Balance: (5.899 + 15.011), Address: '0x765k....q67h', ImageURI: '' }
      ] 
    }
  }
}
</script>
