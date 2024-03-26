<script setup lang="ts">
import { ref } from 'vue'
// common components
import { UserCircleIcon, BellIcon, ArticleIcon, LockIcon } from 'vue-tabler-icons'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'

/* import tabler icons */

// components
import AccountTab from '@/components/pages/account-settings/AccountTab.vue'
import NotificationTab from '@/components/pages/account-settings/NotificationTab.vue'
import BillsTab from '@/components/pages/account-settings/BillsTab.vue'
import SecurityTab from '@/components/pages/account-settings/SecurityTab.vue'

/* tab */
const tab = ref(null)

// theme breadcrumb
const page = ref({ title: 'Account Setting' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Account Setting',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row class="justify-center">
    <!--Account Settings tabs-->
    <v-col cols="12" md="12">
      <v-card class=" " elevation="10" rounded="md">
        <v-tabs v-model="tab" bg-color="transparent" color="primary" height="70" min-height="70">
          <v-tab class="text-medium-emphasis" value="Account">
            <user-circle-icon class="mr-2" size="20" />
            Account
          </v-tab>
          <v-tab class="text-medium-emphasis" value="Notification">
            <bell-icon class="mr-2" size="20" />
            Notification
          </v-tab>
          <v-tab class="text-medium-emphasis" value="Bills">
            <article-icon class="mr-2" size="20" />
            Bills
          </v-tab>
          <v-tab class="text-medium-emphasis" value="Security">
            <lock-icon class="mr-2" size="20" />
            Security
          </v-tab>
        </v-tabs>
        <v-divider />
        <v-card-text class="pa-sm-6 pa-3 pb-sm-6 pb-6">
          <v-window v-model="tab">
            <v-window-item value="Account">
              <account-tab />
            </v-window-item>
            <v-window-item value="Notification">
              <notification-tab />
            </v-window-item>
            <v-window-item value="Bills">
              <bills-tab />
            </v-window-item>
            <v-window-item value="Security">
              <security-tab />
            </v-window-item>
          </v-window>
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>
