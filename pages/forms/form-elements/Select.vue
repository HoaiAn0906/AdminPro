<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'
import SelectDefualt from '@/components/forms/form-elements/select/SelectDefault.vue'
import SelectReadonly from '@/components/forms/form-elements/select/SelectReadOnly.vue'
import SelectMultiple from '@/components/forms/form-elements/select/SelectMultiple.vue'
import SelectChip from '@/components/forms/form-elements/select/SelectChip.vue'
import SelectDensity from '@/components/forms/form-elements/select/SelectDensity.vue'
// theme breadcrumb
const page = ref({ title: 'Select' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Select',
    disabled: true,
    href: '#',
  },
])
</script>
<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Select">
        <v-row>
          <!--Select Basic-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Basic">
              <select-defualt />
            </ui-child-card>
          </v-col>
          <!--Select Readonly-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Read only">
              <select-readonly />
            </ui-child-card>
          </v-col>
          <!--Select Multiple-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Multiple">
              <select-multiple />
            </ui-child-card>
          </v-col>
          <!--Select Chip-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Chips">
              <select-chip />
            </ui-child-card>
          </v-col>
          <!--Select Density-->
          <v-col cols="12" sm="12">
            <ui-child-card title="Density">
              <select-density />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
