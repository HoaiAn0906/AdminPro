<script setup lang="ts">
import 'v-calendar/dist/style.css'
import { ref } from 'vue'

import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'

const date = ref(new Date())
const timezone = ref('')

const range = ref({
  start: new Date(2020, 0, 1),
  end: new Date(2020, 0, 5),
})

const page = ref({ title: 'Calendar' })

const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Check dates',
    disabled: true,
    href: '#',
  },
])
</script>
<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12" lg="4" sm="12">
      <ui-parent-card title="Calendar with Date">
        <v-date-picker v-model="date" class="bg-surface" is-expanded />
      </ui-parent-card>
    </v-col>
    <v-col cols="12" lg="4" sm="12">
      <ui-parent-card title="Calendar with Min Date">
        <v-date-picker v-model="date" class="bg-surface" is-expanded :min-date="new Date()" />
      </ui-parent-card>
    </v-col>
    <v-col cols="12" lg="4" sm="12">
      <ui-parent-card title="Calendar with Max Date">
        <v-date-picker v-model="date" class="bg-surface" is-expanded :max-date="new Date()" />
      </ui-parent-card>
    </v-col>

    <v-col cols="12" lg="6" sm="12">
      <ui-parent-card title="Calendar Date & Time">
        <div>
          <div class="flex mb-2">
            <label class="text-gray-600 font-medium">
              <input v-model="timezone" class="mr-1" type="radio" value="" />
              Local
            </label>
            <label class="text-gray-600 font-medium ml-3">
              <input v-model="timezone" class="mr-1" type="radio" value="utc" />
              UTC
            </label>
          </div>
          <v-date-picker v-model="date" class="bg-surface" mode="dateTime" :timezone="timezone" />
        </div>
      </ui-parent-card>
    </v-col>
    <v-col cols="12" lg="6" sm="12">
      <ui-parent-card title="Calendar Date Range">
        <v-date-picker v-model="range" class="bg-surface" is-range />
      </ui-parent-card>
    </v-col>
    <v-col cols="12" lg="12" sm="12">
      <ui-parent-card title="Calendar Month Steps">
        <v-date-picker v-model="date" class="bg-surface" :rows="2" :step="1" />
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
