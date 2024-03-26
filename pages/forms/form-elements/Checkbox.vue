<script setup lang="ts">
import { ref } from 'vue'
// common components
import { AccessPointIcon } from 'vue-tabler-icons'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'
// icons
import BasicCheckboxes from '@/components/forms/form-elements/checkbox/BasicCheckboxes.vue'
import LabelCheckboxes from '@/components/forms/form-elements/checkbox/LabelCheckboxes.vue'
import ColorCheckboxes from '@/components/forms/form-elements/checkbox/ColorCheckboxes.vue'
import Custom from '@/components/forms/form-elements/checkbox/CustomCheckbox.vue'
// theme breadcrumb
const page = ref({ title: 'Checkboxes' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Checkboxes',
    disabled: true,
    href: '#',
  },
])
</script>

// ===============================|| Ui Checkbox ||=============================== //
<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Checkbox">
        <v-row>
          <!-- Custom checkboxes -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Custom">
              <custom />
            </ui-child-card>
          </v-col>
          <!-- With Colors -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Colors">
              <color-checkboxes />
            </ui-child-card>
          </v-col>
          <!-- Basic checkboxes -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Default">
              <basic-checkboxes />
            </ui-child-card>
          </v-col>
          <!-- With label -->
          <v-col cols="12" lg="6">
            <ui-child-card title="States">
              <label-checkboxes />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
