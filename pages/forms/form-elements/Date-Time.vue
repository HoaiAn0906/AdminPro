<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

/* Components */
import DatePicker from '@/components/forms/form-elements/datetime/DatePicker.vue'
import TimePicker from '@/components/forms/form-elements/datetime/TimePicker.vue'

// theme breadcrumb
const page = ref({ title: 'Date Picker' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Date Time',
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
      <ui-parent-card title="Date Time">
        <v-row>
          <!-- Date Picker -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Date Picker">
              <date-picker />
            </ui-child-card>
          </v-col>
          <!-- Time Picker -->
          <v-col cols="12" lg="6">
            <ui-child-card title="Time Picker">
              <time-picker />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
