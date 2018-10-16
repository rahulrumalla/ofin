<template>
  <v-card
    flat
    class="white primary--text"
    style="border-radius: 5px;">
    <v-card-title 
      class="pb-0">
      <v-layout>
        <v-flex 
          xs8
          class="d1">
          Transactions
        </v-flex>
        <v-flex 
          xs4
          class="text-xs-right">
          <v-btn
            icon
            class="ma-0 primary--text">
            <v-icon medium>fa-qrcode</v-icon>
          </v-btn>
          <v-btn
            icon
            class="ma-0 primary--text">
            <v-icon medium>send</v-icon>
          </v-btn>
          <!-- <v-btn
            icon
            class="ma-0 primary--text">
            <v-icon medium>fa-refresh</v-icon>
          </v-btn> -->
        </v-flex>
      </v-layout>
    </v-card-title>
    <v-card-text>
      <v-layout
        v-for="(t,i) in transactions" 
        :key="i" 
        row
        class="my-4">
        <v-flex 
          xs2
          class="text-xs-center">
          <div class="tt black--text">
            {{ new Date(t.Date).getDate() }}
          </div>
          <div class="subheading mt-2 grey--text">
            {{ getMonthName(t.Date) }} {{ (new Date(t.Date).getFullYear()).toString().substring(2) }}
          </div>
        </v-flex>
        <v-flex xs6>
          <div class="tt">
            <!-- <span class="pr-1">
              <v-icon 
                :class="`${t.Color}--text`"
                medium>
                lens
              </v-icon>
            </span> -->
            {{ t.Merchant }}
          </div>
          <div class="subheading grey--text mt-2">Metamask Main</div>
        </v-flex>
        <v-flex 
          class="text-xs-right"
          xs4>
          <div :class="{'tt red--text': t.Amount < 0, 'tt green--text': t.Amount > 0}">
            {{ t.Amount.toFixed(3) }}
            <span class="pl-1">{{ t.Currency }}</span>
          </div>
          <div class="subheading grey--text mt-2">
            {{ (t.Amount * 212).toFixed(2) }}
            <span class="pl-1">USD</span>
          </div>
        </v-flex>
        <v-flex>
          <v-btn 
            icon>
            <v-icon 
              medium
              class="grey--text">
              more_vert
            </v-icon>
          </v-btn>
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
            Show More Transactions
          </v-btn>
        </v-flex>
      </v-layout>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  data () {
    return {
      transactions: [
        {Date: '24 Sep 2018', Merchant: 'Pizza Hut', Amount: -0.054, Currency: 'ETH', Color: 'purple'},
        {Date: '23 Sep 2018', Merchant: 'Fisherman Arms', Amount: -0.008, Currency: 'ETH', Color: 'purple'},
        {Date: '21 Sep 2018', Merchant: 'DevCon4 Ticket', Amount: -2.519, Currency: 'ETH', Color: 'pink'},
        {Date: '19 Sep 2018', Merchant: 'Gitcoin Bounty', Amount: +0.500, Currency: 'ETH', Color: 'success'}
      ]
    }
  },
  methods: {
    getMonthName(d) {
      const months = ['Jan', 'Feb', 'Mar', 'Apr', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec']
      let date = new Date(d)
      return months[date.getMonth()-1]
    }
  }
}
</script>

