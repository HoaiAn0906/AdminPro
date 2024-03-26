<script setup lang="ts">
import { ref } from 'vue'
import ProductDetail from '@/components/apps/ecommerce/detail/ProductDetail.vue'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import RelatedProducts from '@/components/apps/ecommerce/detail/RelatedProducts.vue'
import ProductTab from '@/components/apps/ecommerce/detail/ProductTab.vue'

const page = ref({ title: 'Products' })
const breadcrumbs = ref([
  {
    text: 'Ecommerce',
    disabled: false,
    href: '#',
  },
  {
    text: 'product Page',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <v-card elevation="10">
        <v-card-text><product-detail /></v-card-text>
      </v-card>
    </v-col>
    <v-col cols="12">
      <product-tab />
    </v-col>
    <v-col cols="12">
      <related-products />
    </v-col>
  </v-row>
</template>
