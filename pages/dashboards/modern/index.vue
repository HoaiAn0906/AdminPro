<script setup lang="ts">
import { ref } from 'vue'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import CongratulationCard from '@/components/dashboards/modern/CongratulationCard.vue'
import Purchases from '@/components/dashboards/modern/Purchases.vue'
import TotalEarnings from '@/components/dashboards/modern/TotalEarnings.vue'
import MonthlyEarnings from '@/components/dashboards/modern/MonthlyEarnings.vue'
import Customers from '@/components/dashboards/modern/Customers.vue'
import TheWeatherCard from '@/components/dashboards/analytical/TheWeatherCardVue.vue'
import TotalSales from '@/components/dashboards/modern/TotalSales.vue'
import ProductPerformance from '@/components/dashboards/modern/ProductPerformance.vue'
import TheProfileCard from '@/components/dashboards/analytical/TheProfileCard.vue'
import TheMyContacts from '@/components/dashboards/analytical/TheMyContacts.vue'
import TheActivityTimeline from '@/components/dashboards/analytical/TheActivityTimeline.vue'
import TheBlogCard from '@/components/dashboards/minimal/TheBlogCard.vue'
import WeeklyStats from '@/components/dashboards/minimal/WeeklyStats.vue'
import MedicalProBranding from '@/components/dashboards/minimal/MedicalProBranding.vue'
import ThecountriesVisits from '@/components/dashboards/modern/ThecountriesVisits.vue'
const page = ref({ title: 'Modern' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Modern',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <!---Congratulation card---->
    <v-col cols="12" lg="5" sm="12">
      <congratulation-card />
    </v-col>
    <!---Purchase / Total earnings---->
    <v-col cols="12" lg="7" sm="12">
      <v-row>
        <v-col lg="5">
          <purchases />
        </v-col>
        <v-col lg="7">
          <total-earnings />
        </v-col>
      </v-row>
    </v-col>
    <!---Revenue updates---->
    <v-col cols="12" lg="8" sm="12">
      <thecountries-visits />
    </v-col>
    <!---Monthly earnings / Customers---->
    <v-col cols="12" lg="4" sm="12">
      <customers />
      <monthly-earnings />
      <the-weather-card class="mt-7" />
    </v-col>
    <!---Total sales---->
    <v-col cols="12" lg="4" sm="12">
      <total-sales />
    </v-col>
    <!---Product performence---->
    <v-col cols="12" lg="8" sm="12">
      <product-performance />
    </v-col>
    <!---Profile card / My contact---->
    <v-col cols="12" lg="4" sm="12">
      <the-profile-card />
      <div class="mt-7" />
      <the-my-contacts />
    </v-col>
    <!---Activity timeline---->
    <v-col cols="12" lg="8" sm="12">
      <the-activity-timeline />
    </v-col>
    <!---Blog card---->
    <v-col cols="12" lg="4">
      <the-blog-card />
    </v-col>
    <!---Weekly stats---->
    <v-col cols="12" lg="4">
      <weekly-stats />
    </v-col>
    <!---Mediacal pro branding---->
    <v-col cols="12" lg="4">
      <medical-pro-branding />
    </v-col>
  </v-row>
</template>
