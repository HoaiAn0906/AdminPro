<script setup lang="ts">
import { ref } from 'vue'

import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import TheSalesOverview from '@/components/dashboards/analytical/TheSalesOverview.vue'
import TotalSales from '@/components/dashboards/analytical/TotalSales.vue'
import TheEarningCard from '@/components/dashboards/minimal/TheEarningCard.vue'
import BlogCard from '@/components/dashboards/analytical/BlogCard.vue'
import NewsletterCampaign from '@/components/dashboards/analytical/NewsletterCampaign.vue'
import TheBandwidthUsage from '@/components/dashboards/analytical/TheBandwidthUsage.vue'
import TheDownloadCount from '@/components/dashboards/analytical/TheDownloadCount.vue'
import TheWeatherCard from '@/components/dashboards/analytical/TheWeatherCardVue.vue'
import RecentComments from '@/components/dashboards/minimal/RecentComments.vue'
import ToDoList from '@/components/dashboards/analytical/ToDoList.vue'

const page = ref({ title: 'Analytical' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Analytical',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <!---Sales overview--->
    <v-col cols="12" lg="8" sm="12">
      <the-sales-overview />
    </v-col>
    <!---Our visiters--->
    <v-col cols="12" lg="4" sm="12">
      <total-sales />
    </v-col>
    <!---TheEarningCard--->
    <v-col class="mt-3" cols="12">
      <the-earning-card />
    </v-col>
    <!---Blog cards--->
    <v-col cols="12" lg="4" sm="12">
      <blog-card />
    </v-col>
    <!---Newsletter Campaign--->
    <v-col cols="12" lg="8" sm="12">
      <newsletter-campaign />
    </v-col>
    <!---Bandwidth usage--->
    <v-col cols="12" lg="4" sm="12">
      <the-bandwidth-usage />
    </v-col>
    <!---Download count--->
    <v-col cols="12" lg="4" sm="12">
      <the-download-count />
    </v-col>
    <!---Weather Card--->
    <v-col cols="12" lg="4" sm="12">
      <the-weather-card />
    </v-col>
    <!---Recent Commments--->
    <v-col cols="12" lg="6" sm="12">
      <recent-comments />
    </v-col>
    <!---The TodoList--->
    <v-col cols="12" lg="6" sm="12">
      <to-do-list />
    </v-col>
  </v-row>
</template>
