<script setup lang="ts">
import { ref } from 'vue'
/* import tabler icons */
import { TrashIcon, SendIcon, BellIcon } from 'vue-tabler-icons'
// common components
import { AccessPointIcon } from 'vue-tabler-icons'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

// icons
import BaseButtons from '@/components/forms/form-elements/button/BaseButtons.vue'
import ColorsButtons from '@/components/forms/form-elements/button/ColorsButtons.vue'
import OutlinedButtons from '@/components/forms/form-elements/button/OutlinedButtons.vue'
import IconsButtons from '@/components/forms/form-elements/button/IconsButtons.vue'
import SizeButtons from '@/components/forms/form-elements/button/SizeButtons.vue'
import TextButtons from '@/components/forms/form-elements/button/TextButtons.vue'
import OutlineIconColor from '@/components/forms/form-elements/button/OutlineIconColor.vue'
import OutlineSizes from '@/components/forms/form-elements/button/OutlineSizes.vue'
import OutlinedIconSize from '@/components/forms/form-elements/button/OutlinedIconSize.vue'
import IconColor from '@/components/forms/form-elements/button/IconColor.vue'
import IconColorSizes from '@/components/forms/form-elements/button/IconColorSizes.vue'
import Default from '@/components/forms/form-elements/button/buttonGroup/Default.vue'
import Text from '@/components/forms/form-elements/button/buttonGroup/Text.vue'
import Plain from '@/components/forms/form-elements/button/buttonGroup/Plain.vue'
import Outlined from '@/components/forms/form-elements/button/buttonGroup/Outlined.vue'

// theme breadcrumb
const page = ref({ title: 'Buttons' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Buttons',
    disabled: true,
    href: '#',
  },
])

// buttons color data
const btnsColor = ref(['primary', 'secondary', 'success', 'error', 'warning'])
</script>

// ===============================|| Ui Buttons ||=============================== //
<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Buttons">
        <v-row>
          <!-- Base Buttons -->
          <v-col cols="12" sm="12">
            <ui-child-card title="Base">
              <base-buttons />
            </ui-child-card>
          </v-col>
          <!-- Color Buttons -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Colors">
              <colors-buttons />
            </ui-child-card>
          </v-col>
          <!-- Sizes -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Size">
              <size-buttons />
            </ui-child-card>
          </v-col>
          <!-- Outlined Buttons -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Outlined">
              <outlined-buttons />
            </ui-child-card>
          </v-col>
          <!-- With Icons -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Outlined Icon">
              <icons-buttons />
            </ui-child-card>
          </v-col>

          <!-- OutlineSizes -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Outline Size">
              <outline-sizes />
            </ui-child-card>
          </v-col>
          <!-- Text Buttons -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Text Color">
              <text-buttons />
            </ui-child-card>
          </v-col>
          <!-- Icon Color -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Icon Color">
              <icon-color />
            </ui-child-card>
          </v-col>
          <!-- Outllined Icon Button -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Outlined Icon Color">
              <outline-icon-color />
            </ui-child-card>
          </v-col>
          <!-- Icon Color Sizes -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Icon Size">
              <icon-color-sizes />
            </ui-child-card>
          </v-col>
          <!-- Outllined Icon Button -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Outlined Icon Size">
              <outlined-icon-size />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>

    <v-col cols="12">
      <ui-parent-card title="Button Group">
        <v-row>
          <!-- Default -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Default">
              <default />
            </ui-child-card>
          </v-col>
          <!-- Text -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Text">
              <text />
            </ui-child-card>
          </v-col>
          <!-- Plain -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Plain">
              <plain />
            </ui-child-card>
          </v-col>
          <!-- Outlined -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Outlined">
              <outlined />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
