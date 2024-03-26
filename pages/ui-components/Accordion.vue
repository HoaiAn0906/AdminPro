<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

import Basic from '@/components/ui-components/expansionpanel/Basic.vue'
import DefaultExpand from '@/components/ui-components/expansionpanel/DefaultExpand.vue'
import Inset from '@/components/ui-components/expansionpanel/Inset.vue'
import Popout from '@/components/ui-components/expansionpanel/Popout.vue'
import CustomizedIcon from '@/components/ui-components/expansionpanel/CustomizedIcon.vue'
import Advance from '@/components/ui-components/expansionpanel/Advance.vue'
// theme breadcrumb
const page = ref({ title: 'Accordian' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Accordian',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Accordian">
        <v-row>
          <!-- Basic -->
          <v-col cols="12">
            <ui-child-card title="Basic">
              <basic />
            </ui-child-card>
          </v-col>
          <!-- Default Expand -->
          <v-col cols="12" lg="12">
            <ui-child-card title="Default Expand">
              <default-expand />
            </ui-child-card>
          </v-col>
          <!-- Inset -->
          <v-col cols="12" lg="12">
            <ui-child-card title="Inset">
              <inset />
            </ui-child-card>
          </v-col>
          <!-- Popout -->
          <v-col cols="12" lg="12">
            <ui-child-card title="Popout">
              <popout />
            </ui-child-card>
          </v-col>
          <!-- Advance -->
          <v-col cols="12" lg="12">
            <ui-child-card title="Advance">
              <advance />
            </ui-child-card>
          </v-col>

          <!-- Customized Icon -->
          <v-col cols="12">
            <ui-child-card title="Customized Icon">
              <customized-icon />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
