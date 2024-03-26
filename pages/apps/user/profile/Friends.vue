<script setup lang="ts">
import { ref, onMounted, computed } from 'vue'
import { HeartIcon, UsersIcon, TrashIcon } from 'vue-tabler-icons'

import ProfileBanner from '@/components/apps/user-profile/ProfileBanner.vue'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import { useFrinedsStore } from '@/stores/apps/userprofile/friends'

const store = useFrinedsStore()

onMounted(() => {
  store.fetchFrineds()
})

const getfriends: any = computed(() => {
  return store.friends
})
const searchValue = ref('')
// dropdown data
const actionDD = ref([
  { title: 'Favorite', icon: HeartIcon },
  { title: 'Edit Friend List', icon: UsersIcon },
  { title: 'Remove', icon: TrashIcon },
])
const page = ref({ title: 'Social Profile' })

const filteredCards = computed(() => {
  return getfriends.value.filter((card: any) => {
    return card.name.toLowerCase().includes(searchValue.value.toLowerCase())
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
          Friends
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
            placeholder="Search Friends"
            prepend-inner-icon="mdi-magnify"
            variant="outlined"
          />
        </v-sheet>
      </div>

      <v-row>
        <v-col v-for="(card, i) in filteredCards" :key="i" cols="12" md="4" sm="6">
          <v-card class="card-hover" elevation="10">
            <v-card-item class="text-center">
              <v-avatar size="80">
                <img :alt="card.avatar" :src="card.avatar" width="80" />
              </v-avatar>
              <h4 class="text-h5 mt-3">{{ card.name }}</h4>
              <span class="text-truncate d-block gap-2 text-subtitle-1">
                {{ card.role }}
              </span>
            </v-card-item>
            <v-divider />
            <v-sheet class="bg-grey100 px-4 py-2 d-flex align-center justify-center gap-2">
              <v-btn class="text-facebook" color="primary" icon size="x-small" variant="text">
                <BrandFacebookIcon size="16" />
              </v-btn>
              <v-btn class="text-instagram" color="primary" icon size="x-small" variant="text">
                <BrandInstagramIcon size="16" />
              </v-btn>
              <v-btn class="text-github" color="primary" icon size="x-small" variant="text">
                <BrandGithubIcon size="16" />
              </v-btn>
              <v-btn class="text-twitter" color="primary" icon size="x-small" variant="text">
                <BrandTwitterIcon size="16" />
              </v-btn>
            </v-sheet>
          </v-card>
        </v-col>
      </v-row>
    </v-col>
  </v-row>
</template>

<style lang="scss" scoped>
.text-facebook {
  color: rgb(24, 119, 242) !important;
}
.text-instagram {
  color: rgb(215, 51, 109) !important;
}
.text-github {
  color: rgb(0, 96, 151) !important;
}
.text-twitter {
  color: rgb(28, 156, 234) !important;
}
</style>
