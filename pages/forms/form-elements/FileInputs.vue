<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'
import FileAccept from '@/components/forms/form-elements/fileinput/FileInputAccept.vue'
import FileChips from '@/components/forms/form-elements/fileinput/FileInputChips.vue'
import FileCounter from '@/components/forms/form-elements/fileinput/FileInputCounter.vue'
import FileDensity from '@/components/forms/form-elements/fileinput/FileInputDensity.vue'
import FileMultiple from '@/components/forms/form-elements/fileinput/FileInputMultiple.vue'
import FilePrepand from '@/components/forms/form-elements/fileinput/FileInputPrepand.vue'
import FileValidation from '@/components/forms/form-elements/fileinput/FileInputValidation.vue'
import FileSelection from '@/components/forms/form-elements/fileinput/FileInputSelection.vue'
// theme breadcrumb
const page = ref({ title: 'File Inputs' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'File Inputs',
    disabled: true,
    href: '#',
  },
])
</script>
<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="File Inputs">
        <v-row>
          <!-- File accept-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Accept">
              <file-accept />
            </ui-child-card>
          </v-col>
          <!-- File chips-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Chips">
              <file-chips />
            </ui-child-card>
          </v-col>
          <!-- File counter-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Counter">
              <file-counter />
            </ui-child-card>
          </v-col>
          <!-- File density-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Density">
              <file-density />
            </ui-child-card>
          </v-col>
          <!-- File multiple-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Multiple">
              <file-multiple />
            </ui-child-card>
          </v-col>
          <!-- File prepend icon-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Prepend Icon">
              <file-prepand />
            </ui-child-card>
          </v-col>
          <!-- File validation-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Validation">
              <file-validation />
            </ui-child-card>
          </v-col>
          <!-- File selection slots-->
          <v-col cols="12" sm="6">
            <ui-child-card title="Complex selection slots">
              <file-selection />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
