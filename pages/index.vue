<template>
  <v-container>
    <v-layout 
      row 
      wrap>
      <v-flex
        xs12 
        md6   
        class="pa-1">
        <v-card 
          flat
          class="mock-widget-card indigo accent-4 white--text">
          <v-card-title>
            <v-layout row>
              <v-flex
                xs8 
                class="hl">
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
      </v-flex>
      <v-flex
        xs12 
        md6 
        class="pa-1">
        <v-card 
          flat
          class="mock-widget-card indigo accent-4 white--text"
        >
          <v-card-title>
            <v-layout row>
              <v-flex 
                xs8
                class="hl">
                Spent Today
              </v-flex>
              <v-flex 
                xs4
                class="text-xs-right">
                <v-btn
                  icon
                  dark
                  class="ma-0">
                  <v-icon medium>fa-line-chart</v-icon>
                </v-btn>
              </v-flex>
            </v-layout>
          </v-card-title>
          <v-card-text>
            <div 
              class="d1">
              120.04
              <sup 
                class="tt">
                USD
              </sup>
            </div>
            <div 
              class="hl blue--text text--accent-1">
              0.891
              <sup 
                class="subheading">
                ETH
              </sup>
            </div>
          </v-card-text>
        </v-card> 
      </v-flex>
    </v-layout>
    <v-layout 
      row 
      wrap 
      class="mt-0">
      <v-flex
        xs12
        md6
        class="pa-1">
        <accounts-list 
          style="min-height: 475px" />
      </v-flex>
      <v-flex 
        xs12
        md6
        class="pa-1">
        <assets-list
          style="min-height: 475px" />
      </v-flex>
    </v-layout>
    <v-layout
      row
      wrap
      class="mt-0">
      <v-flex 
        xs12
        class="pa-1">
        <transactions-list />
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import AccountsList from '~/components/AccountsList'
import AssetsList from '~/components/AssetsList'
import TransactionsList from '~/components/TransactionsList'

export default {
  components: {
    AccountsList,
    AssetsList,
    TransactionsList
  },
  data () {
    return {
      transactionHeaders: [
        {text: 'Date', value: 'Date'},
        {text: 'Merchant', value: 'Merchant'},
        {text: 'Amount', value: 'Amount', align: 'right'}
      ]
    }
  }
}
</script>