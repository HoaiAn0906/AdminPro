<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

import DialogsActivator from '@/components/ui-components/dialogs/DialogsActivator.vue'
import DialogsModel from '@/components/ui-components/dialogs/DialogsModel.vue'
import DialogsFullscreen from '@/components/ui-components/dialogs/DialogsFullscreen.vue'
import DialogsTransitions from '@/components/ui-components/dialogs/DialogsTransitions.vue'
import DialogsPersistent from '@/components/ui-components/dialogs/DialogsPersistent.vue'
import DialogsScrollable from '@/components/ui-components/dialogs/DialogsScrollable.vue'
import DialogsForm from '@/components/ui-components/dialogs/DialogsForm.vue'
import DialogsNested from '@/components/ui-components/dialogs/DialogsNested.vue'
// theme breadcrumb
const page = ref({ title: 'Dialog' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Dialog',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Dialog">
        <v-row>
          <v-col cols="12" lg="4" sm="12">
            <ui-child-card title="Simple">
              <dialogs-activator />
            </ui-child-card>
          </v-col>
          <v-col cols="12" lg="4" sm="12">
            <ui-child-card title="V-model">
              <dialogs-model />
            </ui-child-card>
          </v-col>
          <v-col class="d-flex align-items-stretch" cols="12" lg="4" sm="12">
            <ui-child-card title="Transition">
              <dialogs-transitions />
            </ui-child-card>
          </v-col>
          <v-col class="d-flex align-items-stretch" cols="12" lg="4" sm="12">
            <ui-child-card title="Form">
              <dialogs-form />
            </ui-child-card>
          </v-col>
          <v-col class="d-flex align-items-stretch" cols="12" lg="4" sm="12">
            <ui-child-card title="Full screen">
              <dialogs-fullscreen />
            </ui-child-card>
          </v-col>

          <v-col class="d-flex align-items-stretch" cols="12" lg="4" sm="12">
            <ui-child-card title="Persistent">
              <dialogs-persistent />
            </ui-child-card>
          </v-col>
          <v-col class="d-flex align-items-stretch" cols="12" lg="4" sm="12">
            <ui-child-card title="Scrollable">
              <dialogs-scrollable />
            </ui-child-card>
          </v-col>

          <v-col class="d-flex align-items-stretch" cols="12" lg="4" sm="12">
            <ui-child-card title="Nested Dialog">
              <dialogs-nested />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
