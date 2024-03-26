<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

import FilledColor from '@/components/ui-components/chip/FilledColor.vue'
import Outlined from '@/components/ui-components/chip/Outlined.vue'
import CustomIcon from '@/components/ui-components/chip/CustomIcon.vue'
import CustomIconOutlined from '@/components/ui-components/chip/CustomIconOutlined.vue'
import Disabled from '@/components/ui-components/chip/Disabled.vue'
import Sizes from '@/components/ui-components/chip/Sizes.vue'
import Closable from '@/components/ui-components/chip/Closable.vue'

// theme breadcrumb
const page = ref({ title: 'Chip' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Chip',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Chip">
        <v-row>
          <!-- Filled Color -->
          <v-col cols="12">
            <ui-child-card title="Filled">
              <filled-color />
            </ui-child-card>
          </v-col>
          <!-- Outlined -->
          <v-col cols="12">
            <ui-child-card title="Outlined">
              <outlined />
            </ui-child-card>
          </v-col>
          <!-- Label with Icon -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Custom Icon">
              <custom-icon />
            </ui-child-card>
          </v-col>
          <!-- Outlined Color -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Custom Outlined Icon">
              <custom-icon-outlined />
            </ui-child-card>
          </v-col>
          <!-- Disabled -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Disabled">
              <disabled />
            </ui-child-card>
          </v-col>
          <!-- Sizes -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Sizes">
              <sizes />
            </ui-child-card>
          </v-col>
          <!-- Closable -->
          <v-col cols="12">
            <ui-child-card title="Closable">
              <closable />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
