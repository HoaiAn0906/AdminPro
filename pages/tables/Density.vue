<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import { tableDensityData } from '@/_mockApis/components/table/basicTables'
// theme breadcrumb
const page = ref({ title: 'Density Table' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Density Table',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <!-- ---------------------------------------------------- -->
  <!-- Table Density -->
  <!-- ---------------------------------------------------- -->
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Density Table">
        <!-- <v-table > -->
        <v-card class="border" elevation="0">
          <v-table class="month-table" density="compact">
            <thead>
              <tr>
                <th class="text-h6">User</th>
                <th class="text-h6">Project Name</th>
                <th class="text-h6">Users</th>
                <th class="text-h6">Status</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="item in tableDensityData" :key="item.name" class="month-item">
                <td>
                  <div class="d-flex align-center">
                    <v-avatar size="40">
                      <img alt="avatar" height="40" :src="item.avatar" />
                    </v-avatar>
                    <div class="ml-4">
                      <h6 class="text-h6 text-no-wrap">{{ item.name }}</h6>
                    </div>
                  </div>
                </td>
                <td>
                  <div class="text-subtitle-1 text-no-wrap font-weight-medium text-medium-emphasis">
                    {{ item.post }}
                  </div>
                </td>
                <td>
                  <div class="d-flex align-center">
                    <div class="ml-2 d-flex flex-row-reverse">
                      <v-avatar v-for="user in item.users" :key="user.id" class="ml-n2 avtar-border" size="40">
                        <img alt="avatar" height="40" :src="user.icon" />
                      </v-avatar>
                    </div>
                  </div>
                </td>
                <td>
                  <v-chip class="font-weight-bold py-4 px-3" :color="item.statuscolor" rounded="lg" size="small">
                    {{ item.status }}
                  </v-chip>
                </td>
              </tr>
            </tbody>
          </v-table>
        </v-card>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
