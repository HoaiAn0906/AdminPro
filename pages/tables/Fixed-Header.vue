<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import { tableFixedHeaderData } from '@/_mockApis/components/table/basicTables'
// theme breadcrumb
const page = ref({ title: 'Fixed Header Table' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Fixed Header Table',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <!-- ---------------------------------------------------- -->
  <!-- Table Header Fixed -->
  <!-- ---------------------------------------------------- -->
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Header Fixed Table">
        <v-card class="border" elevation="0">
          <v-table class="month-table" fixed-header height="400px">
            <thead>
              <tr>
                <th class="text-h6">Customer</th>
                <th class="text-h6">Status</th>
                <th class="text-h6">Email Address</th>
                <th class="text-h6">Teams</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="item in tableFixedHeaderData" :key="item.name" class="month-item">
                <td>
                  <div class="d-flex align-center">
                    <v-avatar size="40">
                      <img alt="avatar" height="40" :src="item.avatar" />
                    </v-avatar>
                    <div class="ml-4">
                      <h6 class="text-h6 text-no-wrap">{{ item.name }}</h6>
                      <div class="text-subtitle-1 text-no-wrap font-weight-medium text-medium-emphasis">
                        {{ item.handle }}
                      </div>
                    </div>
                  </div>
                </td>
                <td>
                  <v-chip
                    v-if="item.statusoffline"
                    class="font-weight-bold pl-1 pr-2"
                    :color="item.statuscolor"
                    rounded="lg"
                    size="small"
                  >
                    <ClockHour4Icon class="mr-1" size="15" />
                    {{ item.status }}
                  </v-chip>

                  <v-chip v-else class="font-weight-bold pl-1 pr-2" :color="item.statuscolor" rounded="lg" size="small">
                    <CircleIcon class="mr-1" size="15" />
                    {{ item.status }}
                  </v-chip>
                </td>
                <td>
                  <div class="text-subtitle-1 text-no-wrap font-weight-medium text-medium-emphasis">
                    {{ item.email }}
                  </div>
                </td>
                <td>
                  <div class="d-flex align-center">
                    <div class="d-flex">
                      <v-chip
                        v-for="team in item.teams"
                        :key="team.status"
                        :class="'font-weight-bold px-2 mr-2 bg-' + team.statuscolor"
                        rounded="lg"
                        size="small"
                      >
                        {{ team.status }}
                      </v-chip>
                    </div>
                  </div>
                </td>
              </tr>
            </tbody>
          </v-table>
        </v-card>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
