<script setup lang="ts">
import { ref, onMounted, computed } from 'vue'
import ProfileBanner from '@/components/apps/user-profile/ProfileBanner.vue'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import { useGalleryStore } from '@/stores/apps/userprofile/gallery'
import UiParentCard from '@/components/shared/UiParentCard.vue'

const store = useGalleryStore()

onMounted(() => {
  store.fetchGallery()
})

const getPhotos: any = computed(() => {
  return store.gallery
})
const searchValue = ref('')
// dropdown data
const actionDD = ref([
  { title: 'Remove Tag' },
  { title: 'Download' },
  { title: 'Make Profile Picture' },
  { title: 'Make Cover Photo' },
  { title: 'Find support or Report Photo' },
])
const page = ref({ title: 'Social Profile' })

const filteredCards = computed(() => {
  return getPhotos.value.filter((card: any) => {
    return card.title.toLowerCase().includes(searchValue.value.toLowerCase())
  })
})

const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '/',
  },
  {
    text: 'Social Profile',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <profile-banner />
  <v-row class="justify-content-end mt-5">
    <v-col cols="12">
      <div class="d-sm-flex align-center mb-5">
        <h3 class="text-h3">
          Gallery
          <v-chip class="ml-2 elevation-0" color="secondary" size="small" variant="elevated">
            {{ filteredCards.length }}
          </v-chip>
        </h3>
        <v-sheet class="ml-0 ml-sm-auto mt-3 mt-sm-0" width="250">
          <v-text-field
            v-model="searchValue"
            color="primary"
            density="compact"
            hide-details
            placeholder="Search Gallery"
            prepend-inner-icon="mdi-magnify"
            variant="outlined"
          />
        </v-sheet>
      </div>

      <v-row>
        <v-col v-for="(card, i) in filteredCards" :key="i" cols="12" md="4" sm="6">
          <v-card class="card-hover overflow-hidden" elevation="10">
            <v-avatar class="rounded-0 w-100" size="220">
              <img alt="gallery" :src="card.image" width="450" />
            </v-avatar>
            <v-card-text>
              <div class="d-flex align-center gap-3">
                <div>
                  <h6 class="text-h6 mb-1">{{ card.title }}</h6>
                  <span class="text-subtitle-1 d-block text-truncate d-flex align-center gap-2">
                    {{ card.dateTime }}
                  </span>
                </div>
                <div class="ml-auto">
                  <v-btn color="inherit" icon size="x-small" variant="text">
                    <DotsVerticalIcon stroke-width="1.5" width="14" />
                  </v-btn>
                </div>
              </div>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-col>
  </v-row>
</template>
