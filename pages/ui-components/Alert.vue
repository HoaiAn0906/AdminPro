<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

import Basic from '@/components/ui-components/alert/Basic.vue'
import Filled from '@/components/ui-components/alert/Filled.vue'
import Description from '@/components/ui-components/alert/Description.vue'
import Action from '@/components/ui-components/alert/Action.vue'
import Icons from '@/components/ui-components/alert/Icons.vue'
import Outlined from '@/components/ui-components/alert/Outlined.vue'
import Closable from '@/components/ui-components/alert/Closable.vue'

// theme breadcrumb
const page = ref({ title: 'Alert' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Alert',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Alert">
        <v-row>
          <!-- Basic -->
          <v-col cols="12">
            <ui-child-card title="Basic">
              <basic />
            </ui-child-card>
          </v-col>
          <!-- Filled -->
          <v-col cols="12">
            <ui-child-card title="Filled">
              <filled />
            </ui-child-card>
          </v-col>
          <!-- Outlined -->
          <v-col cols="12">
            <ui-child-card title="Outlined">
              <outlined />
            </ui-child-card>
          </v-col>

          <!-- Description -->
          <v-col cols="12">
            <ui-child-card title="Description">
              <description />
            </ui-child-card>
          </v-col>
          <!-- With Action -->
          <v-col cols="12">
            <ui-child-card title="Action">
              <action />
            </ui-child-card>
          </v-col>
          <!-- With Icons -->
          <v-col cols="12">
            <ui-child-card title="With Icons">
              <icons />
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
