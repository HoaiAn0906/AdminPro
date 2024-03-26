<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

// Components
import BasicLayout from '@/components/forms/form-horizontal/BasicLayout.vue'
import BasicWithIcons from '@/components/forms/form-horizontal/BasicWithIcons.vue'
import FormHrSeprator from '@/components/forms/form-horizontal/FormHrSeprator.vue'
import FormLabelAlign from '@/components/forms/form-horizontal/FormLabelAlign.vue'
import Collapsible from '@/components/forms/form-horizontal/Collapsible.vue'
import PersonalInfoTab from '@/components/forms/form-horizontal/PersonalInfoTab.vue'
import AccountDetailsTab from '@/components/forms/form-horizontal/AccountDetailsTab.vue'
import SocialLinksTab from '@/components/forms/form-horizontal/SocialLinksTab.vue'

/* tab */
const tab = ref(null)

// theme breadcrumb
const page = ref({ title: 'Horizontal Form' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Horizontal Form',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12" md="6">
      <ui-parent-card title="Basic Layout">
        <basic-layout />
      </ui-parent-card>
    </v-col>
    <v-col cols="12" md="6">
      <ui-parent-card title="Basic with Icons">
        <basic-with-icons />
      </ui-parent-card>
    </v-col>
    <v-col cols="12" md="6">
      <form-hr-seprator />
    </v-col>
    <v-col cols="12" md="6">
      <form-label-align />
    </v-col>
    <v-col cols="12">
      <collapsible />
    </v-col>
    <v-col cols="12">
      <h5 class="text-h5 mb-6 mt-3">Form with Tabs</h5>
      <v-card class=" " elevation="10" rounded="md">
        <v-tabs v-model="tab" bg-color="transparent" color="primary">
          <v-tab class="text-medium-emphasis" value="PersonalInfo">Personal Info</v-tab>
          <v-tab class="text-medium-emphasis" value="AccountDetails">Account Details</v-tab>
          <v-tab class="text-medium-emphasis" value="SocialLinks">Social Links</v-tab>
        </v-tabs>
        <v-divider />
        <v-card-text class="pa-sm-6 pa-3 pb-sm-6 pb-6">
          <v-window v-model="tab">
            <v-window-item value="PersonalInfo">
              <personal-info-tab />
            </v-window-item>
            <v-window-item value="AccountDetails">
              <account-details-tab />
            </v-window-item>
            <v-window-item value="SocialLinks">
              <social-links-tab />
            </v-window-item>
          </v-window>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>
