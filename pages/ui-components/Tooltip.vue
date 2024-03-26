<script setup>
import { ref } from 'vue'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'

import SimpleTooltip from '@/components/ui-components/tooltip/SimpleTooltip.vue'
import IconTooltip from '@/components/ui-components/tooltip/IconTooltip.vue'
import ToggleTolltip from '@/components/ui-components/tooltip/ToggleTolltip.vue'
const page = ref({ title: 'Tooltip' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Tooltip',
    disabled: true,
    href: '#',
  },
])
</script>
<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12" md="6">
      <ui-parent-card title="Simple">
        <simple-tooltip />
      </ui-parent-card>
    </v-col>
    <v-col cols="12" md="6">
      <ui-parent-card title="Icon">
        <icon-tooltip />
      </ui-parent-card>
    </v-col>
    <v-col cols="12">
      <ui-parent-card title="Toggle Tolltip">
        <toggle-tolltip />
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
