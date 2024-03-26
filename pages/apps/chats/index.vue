<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import AppBaseCard from '@/components/shared/AppBaseCard.vue'
import ChatListing from '@/components/apps/chats/ChatListing.vue'
import ChatDetail from '@/components/apps/chats/ChatDetail.vue'
import ChatProfile from '@/components/apps/chats/ChatProfile.vue'

// theme breadcrumb
const page = ref({ title: 'Chat app' })

const breadcrumbs = ref([
  {
    text: 'Messenger',
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
      <template #leftpart>
        <chat-profile />
        <chat-listing />
      </template>
      <template #rightpart>
        <chat-detail />
      </template>

      <template #mobileLeftContent>
        <chat-profile />
        <chat-listing />
      </template>
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
