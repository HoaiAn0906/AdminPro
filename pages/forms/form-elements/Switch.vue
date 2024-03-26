<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'
import Default from '@/components/forms/form-elements/switch/Default.vue'
import Label from '@/components/forms/form-elements/switch/Label.vue'
import Inset from '@/components/forms/form-elements/switch/Inset.vue'
import InsetColors from '@/components/forms/form-elements/switch/InsetColors.vue'
import Colors from '@/components/forms/form-elements/switch/Colors.vue'
import States from '@/components/forms/form-elements/switch/States.vue'
// theme breadcrumb
const page = ref({ title: 'Switch' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Switch',
    disabled: true,
    href: '#',
  },
])
</script>

// ===============================|| Ui Switch ||=============================== //
<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Switch">
        <v-row>
          <!-- Default Switch -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Default">
              <default />
            </ui-child-card>
          </v-col>
          <!-- Inset -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Inset">
              <inset />
            </ui-child-card>
          </v-col>
          <!-- With Label -->
          <v-col cols="12" lg="6">
            <ui-child-card title="With Label">
              <label />
            </ui-child-card>
          </v-col>
          <!-- States -->
          <v-col cols="12" lg="6">
            <ui-child-card title="States">
              <states />
            </ui-child-card>
          </v-col>
          <!-- Colors -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Colors">
              <colors />
            </ui-child-card>
          </v-col>
          <!-- Inset Colors -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Inset Colors">
              <inset-colors />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
