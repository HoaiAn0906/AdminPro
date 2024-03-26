<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'
import OrdinaryForm from '@/components/forms/form-layouts/OrdinaryForm.vue'
import InputVarients from '@/components/forms/form-layouts/InputVarients.vue'
import DefaultForm from '@/components/forms/form-layouts/DefaultForm.vue'
import BasicHeaderForm from '@/components/forms/form-layouts/BasicHeaderForm.vue'
import DisabledForm from '@/components/forms/form-layouts/DisabledForm.vue'
import FormLeftIcon from '@/components/forms/form-layouts/FormLeftIcon.vue'
import FormRightIcon from '@/components/forms/form-layouts/FormRightIcon.vue'
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
    <v-col cols="12">
      <ui-parent-card title="Ordinary Form">
        <ordinary-form />
      </ui-parent-card>
      <ui-parent-card class="mt-6" title="Input Variants">
        <input-varients />
      </ui-parent-card>
      <ui-parent-card class="mt-6" title="Default Form">
        <default-form />
      </ui-parent-card>
      <ui-parent-card class="mt-6" title="Basic Header Form">
        <basic-header-form />
      </ui-parent-card>
      <ui-parent-card class="mt-6" title="Disabled Form">
        <disabled-form />
      </ui-parent-card>
    </v-col>
    <!----input with icon----->
    <v-col cols="12" md="6">
      <ui-parent-card title="Form with Left Icon">
        <form-left-icon />
      </ui-parent-card>
    </v-col>
    <v-col cols="12" md="6">
      <ui-parent-card title="Form with Right Icon">
        <form-right-icon />
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
