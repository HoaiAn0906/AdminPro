<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

import MenusAnchor from '@/components/ui-components/menus/MenusAnchor.vue'
import MenusHover from '@/components/ui-components/menus/MenusHover.vue'
import MenusActivatorTooltip from '@/components/ui-components/menus/MenusActivatorTooltip.vue'
import MenusPopover from '@/components/ui-components/menus/MenusPopover.vue'

const page = ref({ title: 'Menus' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Menus',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <ui-parent-card title="Menus">
      <v-row>
        <v-col cols="12" lg="6" sm="12">
          <ui-child-card title="Anchor">
            <menus-anchor />
          </ui-child-card>
        </v-col>
        <v-col cols="12" lg="6" sm="12">
          <ui-child-card title="Hover">
            <menus-hover />
          </ui-child-card>
        </v-col>
        <v-col cols="12" lg="6" sm="12">
          <ui-child-card title="Activator and tooltip">
            <menus-activator-tooltip />
          </ui-child-card>
        </v-col>
        <v-col cols="12" lg="6" sm="12">
          <ui-child-card title="Popover">
            <menus-popover />
          </ui-child-card>
        </v-col>
      </v-row>
    </ui-parent-card>
  </v-row>
</template>
