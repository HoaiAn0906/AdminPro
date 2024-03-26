<script setup lang="ts">
import { ref } from 'vue'
// common components
import { UserIcon, SearchIcon, FolderIcon, ContrastIcon } from 'vue-tabler-icons'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

// icons
import ImageAvatar from '@/components/ui-components/avatar/ImageAvatar.vue'
import LetterAvatar from '@/components/ui-components/avatar/LetterAvatar.vue'
import IconAvatar from '@/components/ui-components/avatar/IconAvatar.vue'
import VariantAvatar from '@/components/ui-components/avatar/VariantAvatar.vue'
import SizeAvatar from '@/components/ui-components/avatar/SizeAvatar.vue'

// theme breadcrumb
const page = ref({ title: 'Avatar' })
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Avatar',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Avatar">
        <v-row>
          <!-- Image Avatar -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Image Avatars">
              <image-avatar />
            </ui-child-card>
          </v-col>
          <!-- Letter Avatar -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Letter Avatars">
              <letter-avatar />
            </ui-child-card>
          </v-col>
          <!-- Icon Avatar -->
          <v-col cols="12" lg="4">
            <ui-child-card title="Icon Avatars">
              <icon-avatar />
            </ui-child-card>
          </v-col>
          <!-- Variant Avatar -->
          <v-col cols="12" lg="4">
            <ui-child-card class="pb-10" title="Variant">
              <variant-avatar />
            </ui-child-card>
          </v-col>
          <!-- Size Avatar -->
          <v-col cols="12" lg="8">
            <ui-child-card title="Sizes">
              <size-avatar />
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
