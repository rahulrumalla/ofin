<template>
  <tabbed-headers-layout>
    <v-card
      flat
      class="white mt-2"
      style="border-radius: 5px;">
      <v-card-title
        class="primary--text d1 px-3">
        X-Change
      </v-card-title>
      <v-card-text>
        <v-layout 
          row 
          wrap>
          <v-flex
            xs6
            md2
            class="pr-2">
            <v-select 
              :items="assetsAvailable"
              v-model="selectedMakerAsset"
              return-object
              placeholder="Your Asset"
              item-text="name"
              item-value="name"
              outline
              class="asset-select primary--text">
              <template 
                slot="selection" 
                slot-scope="data">
                <v-avatar>
                  <v-img 
                    :src="data.item.imageUrl" 
                    height="22"
                    contain />
                </v-avatar>
                <span>
                  {{ data.item.name }}
                </span>
              </template>
              <template 
                slot="item" 
                slot-scope="data"
                class="primary--text">
                <v-avatar>
                  <v-img 
                    :src="data.item.imageUrl" 
                    height="22"
                    contain />
                </v-avatar>
                <span>
                  {{ data.item.name }} 
                  <span class="blue--text text--accent-1">{{ data.item.balance.toFixed(8) }}</span>
                </span>
              </template>
            </v-select>
          </v-flex>
          <v-flex
            xs6
            md3> 
            <v-text-field
              v-model="selectedMakerAssetQuantity"
              type="number"
              label="Amount"
              outline
              clearable
              single-line
            />
          </v-flex>
          <v-flex 
            xs12
            md2
            class="hidden-sm-and-down text-md-center py-3">
            <v-icon>
              fa-exchange
            </v-icon>
          </v-flex>
          <v-flex
            xs6
            md2
            class="pr-2">
            <v-select 
              :items="assetsAvailable"
              v-model="selectedTakerAsset"
              return-object
              placeholder="For Asset"
              item-text="name"
              outline
              hide-selected
              class="asset-select primary--text">
              <template 
                slot="selection" 
                slot-scope="data">
                <v-avatar>
                  <v-img 
                    :src="data.item.imageUrl" 
                    height="22"
                    contain />
                </v-avatar>
                <span class="ml-0">
                  {{ data.item.name }}
                </span>
              </template>
              <template 
                slot="item" 
                slot-scope="data"
                class="primary--text">
                <v-avatar>
                  <v-img 
                    :src="data.item.imageUrl" 
                    height="22"
                    contain />
                </v-avatar>
                <span class="ml-0">
                  {{ data.item.name }} 
                  <span class="blue--text text--accent-1">{{ data.item.balance.toFixed(2) }}</span>
                </span>
              </template>
            </v-select>
          </v-flex>
          <v-flex
            xs6
            md3>
            <v-text-field
              :value="exchangeRate(selectedMakerAsset.name, selectedTakerAsset.name)"
              outline
              single-line
              readonly
            />
          </v-flex>
        </v-layout>
        <div class="py-4 tt">
          You are exchanging 
          <span class="blue--text text--accent-3">
            {{ selectedMakerAssetQuantity }} {{ selectedMakerAsset.name }} 
          </span>
          for 
          <span class="blue--text text--accent-3">
            {{ selectedTakerAssetQuantity }} {{ selectedTakerAsset.name }}
          </span>
        </div>
      </v-card-text>
      <v-card-actions class="px-3 pt-0 pb-4">
        <v-btn
          depressed
          large
          class="error">
          Clear
        </v-btn>
        <v-spacer />
        <v-btn
          depressed
          large
          class="primary">
          X-Change
        </v-btn>
      </v-card-actions>
    </v-card>
  </tabbed-headers-layout>
</template>

<script>
import TabbedHeadersLayout from '~/components/xchange/TabbedHeadersLayout'

export default {
  components: {
    TabbedHeadersLayout
  },
  data () {
    return {
      assetsAvailable: [
        { name: 'ETH', imageUrl: 'https://manager.balance.io/static/media/eth.5e8d1d90.svg', balance: 0.00 },
        { name: 'BLT', imageUrl: 'https://manager.balance.io/tokens/images/0x107c4504cd79c5d2696ea0030a8dd4e92601b82e.png', balance: 0.00 },
        { name: 'ANT', imageUrl: 'https://manager.balance.io/tokens/images/0x960b236a07cf122663c4303350609a66a7b288c0.png', balance: 0.00 },
        { name: 'ZRX', imageUrl: 'https://manager.balance.io/tokens/images/0xe41d2489571d322189246dafa5ebde1f4699f498.png', balance: 0.00 }
      ],
      selectedMakerAsset: {},
      selectedMakerAssetQuantity: 0,
      selectedTakerAsset: {},
      selectedTakerAssetQuantity: 0,
    }
  },
  methods: {
    exchangeRate (makerAsset, takerAsset) {
      if (makerAsset == undefined || takerAsset == undefined) {
        return 'Your Exchange Rate'
      }

      return `${this.selectedMakerAssetQuantity} ${takerAsset} (300 USD)`
    }
  }
}
</script>

<style>
.asset-select.v-select.v-text-field--enclosed:not(.v-text-field--single-line) .v-select__selections {
    padding-top: 2px;
    padding-bottom: 2px;
}

.v-text-field--box input, .v-text-field--outline input {
}
</style>
