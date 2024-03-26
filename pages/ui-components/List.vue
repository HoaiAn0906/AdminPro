<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

import SimpleList from '@/components/ui-components/list/SimpleList.vue'
import NestedList from '@/components/ui-components/list/NestedList.vue'
import FolderList from '@/components/ui-components/list/FolderList.vue'
import DisabledList from '@/components/ui-components/list/DisabledList.vue'
import SwitchList from '@/components/ui-components/list/SwitchList.vue'
import RoundedList from '@/components/ui-components/list/RoundedList.vue'
import CustomAlignList from '@/components/ui-components/list/CustomAlignList.vue'
import ScrollableList from '@/components/ui-components/list/ScrollableList.vue'

// theme breadcrumb
const page = ref({ title: 'Lists' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Lists',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="List">
        <v-row>
          <!-- Basic -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Simple List">
              <simple-list />
            </ui-child-card>
          </v-col>
          <!-- Nested List -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Nested List">
              <nested-list />
            </ui-child-card>
          </v-col>
          <!-- Folder List -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Folder List">
              <folder-list />
            </ui-child-card>
          </v-col>
          <!-- DisabledList-->
          <v-col cols="12" lg="6">
            <ui-child-card title="Disabled List">
              <disabled-list />
            </ui-child-card>
          </v-col>
          <!-- Radio Button List -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Switch List">
              <switch-list />
            </ui-child-card>
          </v-col>

          <!-- Rounded List -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Rounded List">
              <rounded-list />
            </ui-child-card>
          </v-col>
          <!-- Custom Aligned List -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Custom Aligned List">
              <custom-align-list />
            </ui-child-card>
          </v-col>
          <!-- Scrollable List -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Scrollable List">
              <scrollable-list />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
