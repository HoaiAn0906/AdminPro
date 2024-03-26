<script setup lang="ts">
import { ref } from 'vue'
// common components
import {
  UserIcon,
  UserPlusIcon,
  UsersIcon,
  PhotoIcon,
  StarIcon,
  FileDescriptionIcon,
  CreditCardIcon,
  KeyIcon,
} from 'vue-tabler-icons'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'
// icons

import BasicTabs from '@/components/ui-components/tabs/BasicTabs.vue'
import CenterTabs from '@/components/ui-components/tabs/CenterTabs.vue'
import ColorTabs from '@/components/ui-components/tabs/ColorTabs.vue'
import DisableTabs from '@/components/ui-components/tabs/DisableTabs.vue'
import IconsWithLabelTabs from '@/components/ui-components/tabs/IconsWithLabelTabs.vue'
import IconTabs from '@/components/ui-components/tabs/IconTabs.vue'
import CustomIcons from '@/components/ui-components/tabs/CustomIcons.vue'
import AlignCenterTabs from '@/components/ui-components/tabs/AlignCenterTabs.vue'
import AlignEndTabs from '@/components/ui-components/tabs/AlignEndTabs.vue'
// theme breadcrumb
const page = ref({ title: 'Tabs' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Tabs',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Tabs">
        <v-row>
          <!-- Basic -->
          <v-col cols="12" lg="12">
            <ui-child-card title="Basic">
              <basic-tabs />
            </ui-child-card>
          </v-col>
          <!-- With Icons -->
          <v-col cols="12" lg="12">
            <ui-child-card title="Stacked">
              <icons-with-label-tabs />
            </ui-child-card>
          </v-col>
          <!-- Center -->
          <v-col cols="12" lg="12">
            <ui-child-card title="Center Active">
              <center-tabs />
            </ui-child-card>
          </v-col>
          <!-- Custom Icons -->
          <v-col cols="12" lg="12">
            <ui-child-card title="Custom Icons">
              <custom-icons />
            </ui-child-card>
          </v-col>
          <!-- Align Center -->
          <v-col cols="12" lg="12">
            <ui-child-card title="Align Center">
              <align-center-tabs />
            </ui-child-card>
          </v-col>
          <!-- Align End -->
          <v-col cols="12" lg="12">
            <ui-child-card title="Align End">
              <align-end-tabs />
            </ui-child-card>
          </v-col>
          <!-- Icons -->
          <v-col cols="12" lg="12">
            <ui-child-card title="Icon">
              <icon-tabs />
            </ui-child-card>
          </v-col>
          <!-- Disabled -->
          <v-col cols="12" lg="12">
            <ui-child-card title="Disabled">
              <disable-tabs />
            </ui-child-card>
          </v-col>
          <!-- Colors -->
          <v-col cols="12" lg="12">
            <ui-child-card title="Colors">
              <color-tabs />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
