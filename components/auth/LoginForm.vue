<script setup lang="ts">
import { ref } from 'vue'
import { Form } from 'vee-validate'

/* Social icons */
import google from '~/images/svgs/google-icon.svg'
import facebook from '~/images/svgs/facebook-icon.svg'

const router = useRouter()
const checkbox = ref(false)
const valid = ref(false)
const show1 = ref(false)
const password = ref('')
const username = ref('')
const passwordRules = ref([
  (v: string) => !!v || 'Password is required',
  (v: string) => (v && v.length <= 10) || 'Password must be less than 10 characters',
])
const emailRules = ref([
  (v: string) => !!v || 'E-mail is required',
  (v: string) => /.+@.+\..+/.test(v) || 'E-mail must be valid',
])

function validate() {
  router.push({ path: '/dashboards/modern' })
}
</script>

<template>
  <v-row class="d-flex mb-3">
    <v-col class="pr-2" cols="6" sm="6">
      <v-btn block class="border text-subtitle-1" size="large" variant="outlined">
        <img alt="google" class="mr-2" height="16" :src="google" />
        <span class="d-sm-flex d-none mr-1">Sign in with</span>
        Google
      </v-btn>
    </v-col>
    <v-col class="pl-2" cols="6" sm="6">
      <v-btn block class="border text-subtitle-1" size="large" variant="outlined">
        <img alt="facebook" class="mr-1" height="25" :src="facebook" width="25" />
        <span class="d-sm-flex d-none mr-1">Sign in with</span>
        FB
      </v-btn>
    </v-col>
  </v-row>
  <div class="d-flex align-center text-center mb-6">
    <div class="text-h6 w-100 px-5 font-weight-regular auth-divider position-relative">
      <span class="bg-surface px-5 py-3 position-relative">or sign in with</span>
    </div>
  </div>
  <Form v-slot="{ errors, isSubmitting }" class="mt-5" @submit="validate">
    <v-label class="text-subtitle-1 font-weight-medium pb-2 text-lightText">Username</v-label>
    <VTextField v-model="username" class="mb-8" hide-details="auto" required :rules="emailRules" />
    <v-label class="text-subtitle-1 font-weight-medium pb-2 text-lightText">Password</v-label>
    <VTextField
      v-model="password"
      class="pwdInput"
      hide-details="auto"
      required
      :rules="passwordRules"
      type="password"
    />
    <div class="d-flex flex-wrap align-center my-3 ml-n2">
      <v-checkbox
        v-model="checkbox"
        color="primary"
        hide-details
        required
        :rules="[(v:any) => !!v || 'You must agree to continue!']"
      >
        <template #label class="">Remeber this Device</template>
      </v-checkbox>
      <div class="ml-sm-auto">
        <NuxtLink class="text-primary text-decoration-none text-body-1 opacity-1 font-weight-medium" to="">
          Forgot Password ?
        </NuxtLink>
      </div>
    </div>
    <v-btn block color="primary" :disabled="!password" flat :loading="isSubmitting" size="large" type="submit">
      Sign In
    </v-btn>
    <div v-if="errors.apiError" class="mt-2">
      <v-alert color="error">{{ errors.apiError }}</v-alert>
    </div>
  </Form>
</template>
