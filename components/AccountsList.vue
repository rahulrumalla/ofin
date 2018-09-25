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
          My Accounts
        </v-flex>
        <v-flex 
          xs4
          class="text-xs-right">
          <v-btn
            icon
            class="ma-0 primary--text">
            <v-icon medium>fa-plus</v-icon>
          </v-btn>
          <v-btn
            icon
            class="ma-0 primary--text">
            <v-icon medium>edit</v-icon>
          </v-btn>
        </v-flex>
      </v-layout>
    </v-card-title>
    <v-card-text>
      <v-layout 
        v-for="a in accounts"
        :key="a.Address"
        row
        class="my-4">
        <v-flex 
          xs6>
          <div class="tt">{{ a.Name }}</div>
          <div class="grey--text subheading mt-2">{{ a.Address }}</div>
        </v-flex>
        <v-flex 
          xs6
          class="text-xs-right">
          <div class="tt black--text">{{ a.Balance }} {{ a.Currency }}</div>
          <div class="grey--text subheading mt-2">{{ a.Balance }} USD</div>
        </v-flex>
      </v-layout>
      <v-layout 
        column
        justify-center
        align-center>
        <v-btn
          depressed
          large
          round
          class="primary">
          Show All +3
        </v-btn>
      </v-layout>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  data () {
    return {
      accounts: [
        { Name: 'Metamask Main', Balance: 13.295, Currency: 'ETH', Address: '0xh234....1233', WalletType: 'Crypto' },
        { Name: 'ENS', Balance: 2399.44, Currency: 'DAI', Address: 'mydaiwallet.ens', WalletType: 'Crypto' },
        { Name: 'BTC Main', Balance: 5.899, Currency: 'BTC', Address: '0x765k....q67h', WalletType: 'Crypto' },
        { Name: 'Coinbase BTC', Balance: 15.011, Currency: 'BTC', Address: '0x34ha....po9x', WalletType: 'Crypto' }
      ]
    }
  }
}
</script>
