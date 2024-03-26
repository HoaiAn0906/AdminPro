<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import EditableTable from '@/components/table/EditableTable.vue'
// theme breadcrumb
const page = ref({ title: 'Contact List' })

const breadcrumbs = ref([
  {
    text: '2 New Contacts',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-card elevation="10">
    <v-card-text>
      <editable-table />
    </v-card-text>
  </v-card>
</template>
