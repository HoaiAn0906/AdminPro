<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import CustomForm from '~~/components/forms/form-custom/CustomForm.vue'
// theme breadcrumb
const page = ref({ title: 'Form Layouts' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Form Layouts',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col class="mb-12" cols="12">
      <ui-parent-card title="Custom Form">
        <custom-form />
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
