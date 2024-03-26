<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

import BasicRatting from '@/components/ui-components/ratting/BasicRatting.vue'
import ClearableRatting from '@/components/ui-components/ratting/ClearableRatting.vue'
import HalfRatting from '@/components/ui-components/ratting/HalfRatting.vue'
import HoverRatting from '@/components/ui-components/ratting/HoverRatting.vue'
import IconsRatting from '@/components/ui-components/ratting/IconsRatting.vue'
import LabelRatting from '@/components/ui-components/ratting/LabelRatting.vue'
import ReadOnlyRatting from '@/components/ui-components/ratting/ReadOnlyRatting.vue'
import SizeRatting from '@/components/ui-components/ratting/SizeRatting.vue'
import LengthRatting from '@/components/ui-components/ratting/LengthRatting.vue'

// theme breadcrumb
const page = ref({ title: 'Rating' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Rating',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Rating">
        <v-row>
          <!-- Basic -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Basic">
              <basic-ratting />
            </ui-child-card>
          </v-col>
          <!-- Read Only -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Read Only">
              <read-only-ratting />
            </ui-child-card>
          </v-col>
          <!-- Clearable -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Clearable">
              <clearable-ratting />
            </ui-child-card>
          </v-col>
          <!-- Hover -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Hover">
              <hover-ratting />
            </ui-child-card>
          </v-col>
          <!-- Half Ratting -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Half Ratting">
              <half-ratting />
            </ui-child-card>
          </v-col>
          <!-- Length Ratting -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Length">
              <length-ratting />
            </ui-child-card>
          </v-col>
          <!-- Label -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Label">
              <label-ratting />
            </ui-child-card>
          </v-col>
          <!-- Icons -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Icons">
              <icons-ratting />
            </ui-child-card>
          </v-col>
          <!-- Size -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Size">
              <size-ratting />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
