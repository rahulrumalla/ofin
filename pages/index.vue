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
          <v-card-title 
            class="headline">
            <v-layout row>
              <v-flex
                xs8 
                class="display-1">
                Account Balance
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
              class="display-1">
              1,700.093
              <sup 
                class="title">
                ETH
              </sup>
            </div>
            <div 
              class="headline">
              34,500.04
              <sup 
                class="subheading">
                USD
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
          <v-card-title 
            class="headline">
            <v-layout row>
              <v-flex 
                xs8
                class="display-1">
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
              class="display-1">
              0.891
              <sup 
                class="title">
                ETH
              </sup>
            </div>
            <div 
              class="headline">
              120.04
              <sup 
                class="subheading">
                USD
              </sup>
            </div>
          </v-card-text>
        </v-card> 
      </v-flex>
    </v-layout>
    <div
      class="mt-4">
      <div
        class="headline primary--text grey lighten-4 pb-2 px-1">
        <v-layout>
          <v-flex 
            xs6
            class="display-1">
            Transactions
          </v-flex>
          <v-flex 
            xs6
            class="text-xs-right">
            <v-btn
              icon
              class="ma-0 primary--text">
              <v-icon medium>fa-qrcode</v-icon>
            </v-btn>
            <v-btn
              icon
              class="ma-0 primary--text">
              <v-icon medium>fa-send</v-icon>
            </v-btn>
            <v-btn
              icon
              class="ma-0 primary--text">
              <v-icon medium>fa-refresh</v-icon>
            </v-btn>
          </v-flex>
        </v-layout>
      </div>
      <div
        class="white pa-4"
        style="border-radius: 15px;">
        <v-layout
          v-for="(t,i) in transactions" 
          :key="i" 
          row
          class="headline my-2">
          <v-flex 
            xs8>
            <div>
              <span class="pr-1">
                <v-icon 
                  :class="`${t.Color}--text`"
                  medium>
                  lens
                </v-icon>
              </span>
              {{ t.Merchant }}
            </div>
            <div class="subheading grey--text">{{ t.Date }}</div>
          </v-flex>
          <v-flex 
            class="text-xs-right headline"
            xs4>
            <div :class="{'red--text': t.Amount < 0, 'green--text': t.Amount > 0}">
              {{ t.Amount.toFixed(3) }}
              <span class="pl-1">{{ t.Currency }}</span>
            </div>
            <div class="subheading grey--text">
              {{ (t.Amount * 212).toFixed(2) }}
              <span class="pl-1">USD</span>
            </div>
          </v-flex>
        </v-layout>
        <v-layout 
          column
          align-center
          justify-center>
          <v-flex>
            <v-btn
              large
              round
              depressed
              class="primary subheading">
              Show More
            </v-btn>
          </v-flex>
        </v-layout>
      </div>
    </div>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      transactionHeaders: [
        {text: 'Date', value: 'Date'},
        {text: 'Merchant', value: 'Merchant'},
        {text: 'Amount', value: 'Amount', align: 'right'}
      ],
      transactions: [
        {Date: 'Sept 24, 2018', Merchant: 'Pizza Hut', Amount: -0.054, Currency: 'ETH', Color: 'purple'},
        {Date: 'Sept 23, 2018', Merchant: 'Fisherman Arms', Amount: -0.008, Currency: 'ETH', Color: 'purple'},
        {Date: 'Sept 21, 2018', Merchant: 'DevCon4 Ticket', Amount: -2.519, Currency: 'ETH', Color: 'pink'},
        {Date: 'Sept 19, 2018', Merchant: 'Gitcoin Bounty', Amount: +0.500, Currency: 'ETH', Color: 'success'}
      ]
    }
  }
}
</script>


<style lang="stylus">
.mock-widget-card
  height: 170px;
  border-radius: 15px;
</style>
