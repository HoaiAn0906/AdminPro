<script setup lang="ts">
import { ref } from 'vue'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'
import Heading from '@/components/style-components/typography/Heading.vue'
import Opacity from '@/components/style-components/typography/Opacity.vue'
import TextAlignment from '@/components/style-components/typography/TextAlignment.vue'
import TextDecoration from '@/components/style-components/typography/TextDecoration.vue'
import Default from '@/components/style-components/typography/DefaultText.vue'
const page = ref({ title: 'Typography' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Typography',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12" md="12">
      <ui-parent-card title="Basic Typography">
        <ui-child-card title="Heading">
          <heading />
        </ui-child-card>
        <ui-child-card class="mt-5" title="Default Text">
          <default />
        </ui-child-card>
        <ui-child-card class="mt-5" title="Text-alignment">
          <text-alignment />
        </ui-child-card>
        <ui-child-card class="mt-5" title="Decoration">
          <text-decoration />
        </ui-child-card>
        <ui-child-card class="mt-5" title="Opacity">
          <opacity />
        </ui-child-card>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
