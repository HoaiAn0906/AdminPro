<script setup lang="ts">
import { ref } from 'vue'
// common components
import { AccessPointIcon, MailIcon } from 'vue-tabler-icons'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

// icons
import ComboBox from '@/components/forms/form-elements/autocomplete/ComboBox.vue'
import WithCaption from '@/components/forms/form-elements/autocomplete/WithCaption.vue'
import MultipleOptions from '@/components/forms/form-elements/autocomplete/MultipleOptions.vue'

// theme breadcrumb
const page = ref({ title: 'Autocomplete' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Autocomplete',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Autocomplete">
        <v-row>
          <!-- Combo Box -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Combo Box">
              <combo-box />
            </ui-child-card>
          </v-col>
          <!-- With Caption -->
          <v-col cols="12" lg="4">
            <ui-child-card title="With Caption">
              <with-caption />
            </ui-child-card>
          </v-col>
          <!-- Combo with Multiple Options -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Combo with Multiple Options">
              <multiple-options />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
