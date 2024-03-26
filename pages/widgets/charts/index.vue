<script setup lang="ts">
import { ref } from 'vue'
/* Breadcrumb component */
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'

/* Call Components */
import Followers from '@/components/widgets/charts/Followers.vue'
import Views from '@/components/widgets/charts/Views.vue'
import Earned from '@/components/widgets/charts/Earned.vue'
import TotalEarning from '@/components/widgets/charts/TotalEarning.vue'
import CurrentValue from '@/components/widgets/charts/CurrentValue.vue'
import MostVisited from '@/components/widgets/charts/MostVisited.vue'
import PageImpression from '@/components/widgets/charts/PageImpression.vue'
import YearlyBreakup from '@/components/widgets/charts/YearlyBreakup.vue'
import MonthlyEarnings from '@/components/widgets/charts/MonthlyEarnings.vue'
import YearlySales from '@/components/widgets/charts/YearlySales.vue'
import RevenueUpdates from '@/components/widgets/charts/RevenueUpdates.vue'
import SalesOverview from '@/components/widgets/charts/SalesOverview.vue'
import Customers from '@/components/widgets/charts/Customers.vue'
import Projects from '@/components/widgets/charts/Projects.vue'

// theme breadcrumb
const page = ref({ title: 'Charts' })
const breadcrumbs = ref([
  {
    text: 'Home',
    disabled: false,
    href: '#',
  },
  {
    text: 'Charts',
    disabled: true,
    href: '#',
  },
])
</script>
<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <!-- Followers Chart -->
    <v-col cols="12" sm="3">
      <followers />
    </v-col>
    <!-- Views Chart -->
    <v-col cols="12" sm="3">
      <views />
    </v-col>
    <!-- Earned Chart -->
    <v-col cols="12" sm="3">
      <earned />
    </v-col>
    <!-- TotalEarning Chart -->
    <v-col cols="12" sm="3">
      <total-earning />
    </v-col>
    <!-- Current Value -->
    <v-col cols="12">
      <current-value />
    </v-col>
    <v-col cols="12" md="4">
      <!-- Yearly Breakup -->
      <yearly-breakup />
      <!-- Monthly Earnings -->
      <monthly-earnings />
      <!-- Most Visited -->
      <most-visited />
    </v-col>
    <v-col cols="12" md="4">
      <!-- Yearly Sales -->
      <yearly-sales />
      <!-- Page Impression -->
      <page-impression />
      <v-row class="mt-3">
        <v-col cols="12" sm="6">
          <customers />
        </v-col>
        <v-col cols="12" sm="6">
          <projects />
        </v-col>
      </v-row>
    </v-col>

    <v-col cols="12" md="4">
      <v-row>
        <!-- Revenue Updates -->
        <v-col cols="12">
          <revenue-updates />
        </v-col>
        <!-- Sales Overview -->
        <v-col cols="12">
          <sales-overview />
        </v-col>
      </v-row>
    </v-col>
  </v-row>
</template>
