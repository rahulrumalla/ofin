<template>
  <v-card 
    flat
    class="rounded-card white primary--text">
    <v-card-title
      class="pb-0">
      <v-layout row>
        <v-flex
          xs10
          class="d1">
          Approve Assets
        </v-flex>
        <v-flex 
          xs2
          class="text-xs-right">
          <v-btn
            icon
            class="ma-0 primary--text">
            <v-icon medium>info_outline</v-icon>
          </v-btn>
        </v-flex>
      </v-layout>
    </v-card-title>
    <v-card-text>
      <v-layout 
        v-for="a in assets"
        :key="a.Address"
        row
        class="my-4">
        <v-flex 
          xs6
          class="">
          <div class="tt">{{ a.Name }}</div>
          <div class="subheading mt-2 grey--text">{{ a.Balance }} {{ a.Name }}</div>
        </v-flex>
        <v-spacer />
        <v-flex 
          xs5
          class="">
          <v-switch 
            :label="a.IsEnabled ? 'Enabled' : 'Disabled'" 
            v-model="a.IsEnabled"
            color="primary primary--text" />
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
        { Name: 'WETH', IsEnabled: false, Balance: 1.295, Address: '0xh234....1233', ImageURI: 'https://manager.balance.io/static/media/eth.5e8d1d90.svg' },
        { Name: 'DAI', IsEnabled: false, Balance: 2399.44, Address: 'mydaiwallet.ens', ImageURI: '' }
      ] 
    }
  }
}
</script>
