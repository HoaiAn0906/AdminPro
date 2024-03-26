<script setup lang="ts">
import { ref } from 'vue'
// common components
import FaqQuestion from './FaqQuestion.vue'
import StillHaveQuestions from './StillHaveQuestions.vue'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'

// FAQ components

// theme breadcrumb
const page = ref({ title: 'FAQ' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'FAQ',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />

  <v-row class="justify-center">
    <!--Questions-->
    <v-col cols="12" md="8">
      <faq-question />
    </v-col>
    <!--Stil Have Questions-->
    <v-col cols="12" md="10">
      <still-have-questions />
    </v-col>
  </v-row>
</template>
