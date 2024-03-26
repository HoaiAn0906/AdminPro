<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

import Default from '@/components/forms/form-elements/slider/Default.vue'
import Disabled from '@/components/forms/form-elements/slider/Disabled.vue'
import Volume from '@/components/forms/form-elements/slider/Volume.vue'
import TickSize from '@/components/forms/form-elements/slider/TickSize.vue'
import Steps from '@/components/forms/form-elements/slider/Steps.vue'
import Ticks from '@/components/forms/form-elements/slider/Ticks.vue'
import Vertical from '@/components/forms/form-elements/slider/Vertical.vue'
import Custom from '@/components/forms/form-elements/slider/Custom.vue'

// theme breadcrumb
const page = ref({ title: 'Slider' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Slider',
    disabled: true,
    href: '#',
  },
])
</script>
<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Slider">
        <v-row>
          <!-- Default Slider -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Default">
              <default />
            </ui-child-card>
          </v-col>
          <!-- Volume -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Icon">
              <volume />
            </ui-child-card>
          </v-col>
          <!-- Disabled -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Disabled">
              <disabled />
            </ui-child-card>
          </v-col>
          <!-- Steps -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Steps">
              <steps />
            </ui-child-card>
          </v-col>
          <!-- Ticks -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Ticks">
              <ticks />
            </ui-child-card>
          </v-col>
          <!-- Tick Size-->
          <v-col cols="12" lg="4">
            <ui-child-card title="Tick Size">
              <tick-size />
            </ui-child-card>
          </v-col>
          <!-- Custom-->
          <v-col cols="12" lg="6">
            <ui-child-card title="Custom">
              <custom />
            </ui-child-card>
          </v-col>
          <!-- Vertical Slider -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Vertical">
              <vertical />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
