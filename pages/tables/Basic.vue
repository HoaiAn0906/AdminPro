<script setup lang="ts">
import { ref } from 'vue'
// common components
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'

// Table
import Table1 from '@/components/table/Table1.vue'
import Table2 from '@/components/table/Table2.vue'
import Table3 from '@/components/table/Table3.vue'
import Table4 from '@/components/table/Table4.vue'
import Table5 from '@/components/table/Table5.vue'

// theme breadcrumb
const page = ref({ title: 'Basic Table' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Basic Table',
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
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Basic Table">
        <!--Basic Table 1-->
        <table1 />
        <!--Basic Table 2-->
        <table2 />
        <!--Basic Table 3-->
        <table3 />
        <!--Basic Table 4-->
        <table4 />
        <!--Basic Table 5-->
        <table5 />
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
