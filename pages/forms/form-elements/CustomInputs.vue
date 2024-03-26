<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'
import InputError from '@/components/forms/form-elements/custominput/InputError.vue'
import InputLoading from '@/components/forms/form-elements/custominput/InputLoading.vue'
import InputMultipleError from '@/components/forms/form-elements/custominput/InputMultipleError.vue'
import InputPrepandAppend from '@/components/forms/form-elements/custominput/InputAppendPrepend.vue'
import InputHideDetails from '@/components/forms/form-elements/custominput/InputHideDetails.vue'
import InputRules from '@/components/forms/form-elements/custominput/InputRules.vue'
// theme breadcrumb
const page = ref({ title: 'Custom Inputs' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Custom Inputs',
    disabled: true,
    href: '#',
  },
])
</script>
<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Custom Inputs">
        <v-row>
          <!-- Input error-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Error">
              <input-error />
            </ui-child-card>
          </v-col>
          <!-- Multiple Input error-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Multiple Error">
              <input-multiple-error />
            </ui-child-card>
          </v-col>
          <!-- Input loading-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Loading">
              <input-loading />
            </ui-child-card>
          </v-col>
          <!-- Input Append and prepend-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Append and Prepend">
              <input-prepand-append />
            </ui-child-card>
          </v-col>
          <!-- Input Hide Details-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Hide Details">
              <input-hide-details />
            </ui-child-card>
          </v-col>
          <!-- Input Rules-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Rules">
              <input-rules />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
