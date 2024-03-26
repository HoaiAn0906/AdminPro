<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import AppBaseCard from '@/components/shared/AppBaseCard.vue'
// component
import NotesListing from '@/components/apps/notes/NotesListing.vue'
import NotesContent from '@/components/apps/notes/NotesContent.vue'
// theme breadcrumb
const page = ref({ title: 'Note app' })

const breadcrumbs = ref([
  {
    text: 'Add todo list',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <!-- ---------------------------------------------------- -->
  <!-- Table Basic -->
  <!-- ---------------------------------------------------- -->
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />

  <v-card class="overflow-hidden" elevation="10">
    <app-base-card>
      <template #leftpart><notes-listing /></template>
      <template #rightpart><notes-content /></template>

      <template #mobileLeftContent><notes-listing /></template>
    </app-base-card>
  </v-card>
</template>

<style scoped lang="scss">
@media (max-width: 1279px) {
  .v-card {
    position: unset;
  }
}
</style>
