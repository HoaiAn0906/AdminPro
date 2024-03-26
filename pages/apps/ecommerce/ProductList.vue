<script setup lang="ts">
import { ref, computed, onMounted } from 'vue'
import type { Header, Item } from 'vue3-easy-data-table'
import { format } from 'date-fns'
import { useEcomStore } from '@/stores/apps/eCommerce'
import UiParentCard from '@/components/shared/UiParentCard.vue'
const store = useEcomStore()
onMounted(() => {
  store.fetchProducts()
})

const getProducts = computed(() => {
  return store.products
})

const searchField = ref('name')
const searchValue = ref('')

const headers: Header[] = [
  { text: '#', value: 'image' },
  { text: 'Product name', value: 'name', sortable: true },
  { text: 'Created', value: 'created', sortable: true },
  { text: 'Price', value: 'offerPrice', sortable: true },
  { text: 'sale-price', value: 'salePrice', sortable: true },
  { text: 'status', value: 'isStock' },
  { text: 'Action', value: 'operation' },
]
const items = ref(getProducts)
const themeColor = ref('rgb(var(--v-theme-secondary))')

const itemsSelected = ref<Item[]>([])
</script>

<template>
  <v-row>
    <v-col cols="12" md="12">
      <ui-parent-card title="Product List">
        <v-row class="align-center mb-3" justify="space-between">
          <v-col cols="12" md="3">
            <v-text-field
              v-model="searchValue"
              density="compact"
              hide-details
              placeholder="Search Product"
              prepend-inner-icon="mdi-magnify"
              type="text"
              variant="outlined"
            />
          </v-col>
          <v-col cols="12" md="3">
            <div class="d-flex gap-2 justify-end">
              <v-btn icon variant="text">
                <CopyIcon size="20" />
              </v-btn>
              <v-btn icon variant="text">
                <PrinterIcon size="20" />
              </v-btn>
              <v-btn icon variant="text">
                <FilterIcon size="20" />
              </v-btn>
            </div>
          </v-col>
        </v-row>
        <EasyDataTable
          v-model:items-selected="itemsSelected"
          :headers="headers"
          :items="items"
          :rows-per-page="5"
          :search-field="searchField"
          :search-value="searchValue"
          table-class-name="customize-table"
          :theme-color="themeColor"
        >
          <template #item-image="{ image }">
            <div class="player-wrapper">
              <img alt="product" class="rounded-md" :src="image" width="70" />
            </div>
          </template>
          <template #item-name="{ name }">
            <div class="player-wrapper">
              <h5 class="text-h5">{{ name }}</h5>
            </div>
          </template>
          <template #item-created="{ date }">
            <div class="player-wrapper">
              {{ format(new Date(date), 'E, MMM d') }}
            </div>
          </template>
          <template #item-offerPrice="{ offerPrice }">
            <div class="player-wrapper">
              <h5 class="text-h5">${{ offerPrice }}</h5>
            </div>
          </template>
          <template #item-salePrice="{ salePrice }">
            <div class="player-wrapper">
              <h5 class="text-h5">${{ salePrice }}</h5>
            </div>
          </template>
          <template #item-isStock="{ isStock }">
            <div class="player-wrapper">
              <v-chip v-if="isStock" color="success" size="small">In Stock</v-chip>
              <v-chip v-else color="error" size="small">Out of Stock</v-chip>
            </div>
          </template>

          <template #item-operation="item">
            <div class="operation-wrapper">
              <v-btn icon variant="text">
                <DotsIcon size="18" />
              </v-btn>
            </div>
          </template>
        </EasyDataTable>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
