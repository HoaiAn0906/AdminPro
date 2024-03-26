<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'
import ComboboxDense from '@/components/forms/form-elements/combobox/ComboboxDense.vue'
import ComboboxMultiple from '@/components/forms/form-elements/combobox/ComboboxMultiple.vue'

// theme breadcrumb
const page = ref({ title: 'Combobox' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Combobox',
    disabled: true,
    href: '#',
  },
])
</script>
<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Combobox">
        <v-row>
          <!-- Density Combobox -->
          <v-col cols="12" sm="12">
            <ui-child-card title="Density">
              <combobox-dense />
            </ui-child-card>
          </v-col>
          <!-- Multiple Combobox -->
          <v-col cols="12" sm="12">
            <ui-child-card title="Multiple">
              <combobox-multiple />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
