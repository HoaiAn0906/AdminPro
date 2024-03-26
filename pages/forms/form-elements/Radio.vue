<script setup lang="ts">
import { ref } from 'vue'
// common components
import { AccessPointIcon } from 'vue-tabler-icons'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

// icons
import Default from '@/components/forms/form-elements/radio/Default.vue'
import Label from '@/components/forms/form-elements/radio/Label.vue'
import DefaultDirection from '@/components/forms/form-elements/radio/DefaultDirection.vue'
import InlineDirection from '@/components/forms/form-elements/radio/InlineDirection.vue'
import Color from '@/components/forms/form-elements/radio/Color.vue'
import ColorwithLabel from '@/components/forms/form-elements/radio/LabelwithColor.vue'

// theme breadcrumb
const page = ref({ title: 'Radio' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Radio',
    disabled: true,
    href: '#',
  },
])
</script>

// ===============================|| Ui Radio ||=============================== //
<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Radio">
        <v-row>
          <!-- Default Radio -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Default">
              <default />
            </ui-child-card>
          </v-col>
          <!-- Radio with Label -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Label">
              <label />
            </ui-child-card>
          </v-col>
          <!-- With Colors -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Colors">
              <color />
            </ui-child-card>
          </v-col>
          <!-- With Colors -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Colors with Label">
              <colorwith-label />
            </ui-child-card>
          </v-col>
          <!-- Default Direction -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Default Direction">
              <default-direction />
            </ui-child-card>
          </v-col>
          <!-- Inline Direction -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Inline Direction">
              <inline-direction />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
