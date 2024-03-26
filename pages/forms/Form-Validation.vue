<script setup lang="ts">
import { ref } from 'vue'
// common components
import { Form } from 'vee-validate'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiParentCardLogo from '@/components/shared/UiParentCardLogo.vue'
import VeeValidation from '@/components/forms/form-validation/VeeValidation.vue'
import MailValidation from '@/components/forms/form-validation/MailValidation.vue'
import OnType from '@/components/forms/form-validation/OnType.vue'
import Radio from '@/components/forms/form-validation/Radio.vue'
import CheckBox from '@/components/forms/form-validation/CheckBox.vue'
import SelectBox from '@/components/forms/form-validation/Select.vue'
// theme breadcrumb
const page = ref({ title: 'Form Validation' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Form Validation',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col class="mb-0" cols="12" lg="6">
      <ui-parent-card-logo>
        <vee-validation />
      </ui-parent-card-logo>
    </v-col>
    <v-col class="mb-0" cols="12" lg="6">
      <ui-parent-card-logo>
        <mail-validation />
      </ui-parent-card-logo>
      <ui-parent-card class="mt-6" title="Select">
        <select-box />
      </ui-parent-card>
    </v-col>
    <v-col class="" cols="12" lg="6">
      <ui-parent-card title="On Leave">
        <on-type />
      </ui-parent-card>
    </v-col>
    <v-col class="" cols="12" lg="6">
      <ui-parent-card title="Checkboxes">
        <check-box />
      </ui-parent-card>
    </v-col>
    <v-col class="" cols="12" lg="6">
      <ui-parent-card title="Radio">
        <radio />
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
