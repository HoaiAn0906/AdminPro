<script setup lang="ts">
import { ref } from 'vue'
// common components
import { MailIcon, LockIcon, EyeIcon } from 'vue-tabler-icons'
import BaseBreadcrumb from '@/components/shared/BaseBreadcrumb.vue'
import UiParentCard from '@/components/shared/UiParentCard.vue'
import UiChildCard from '@/components/shared/UiChildCard.vue'

// icons

// define consts
const page = ref({ title: 'Textfield' })
const caption_email1 = ref('demo@company.com')
const caption_email2 = ref('demo@company.com')
const caption_email3 = ref('demo@company.com')
const validate_email1 = ref('demo.sd')
const validate_email2 = ref('demo.sd')
const multiline2 = ref('Default Value')
const select_sm = ref(['Small'])
const select_md = ref('Default')
const full_text = ref('Default')
const some_imp1 = ref('Default')
const some_imp2 = ref('Default')
const some_imp3 = ref('Default')

// rules for email textfield
const rules = ref({
  required: (value: any) => !!value || 'Required.',
  counter: (value: any) => value.length <= 20 || 'Max 20 characters',
  email: (value: any) => {
    const pattern =
      /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
    return pattern.test(value) || 'Invalid e-mail.'
  },
})

//  data of select
const items = ref(['None', 'demo@company.com', 'Judiya@company.com', 'taju_diya@company.com'])

// theme breadcrumb
const breadcrumbs = ref([
  {
    text: 'Dashboard',
    disabled: false,
    href: '#',
  },
  {
    text: 'Textfield',
    disabled: true,
    href: '#',
  },
])
</script>

<template>
  <base-breadcrumb :breadcrumbs="breadcrumbs" :title="page.title" />
  <v-row>
    <v-col cols="12">
      <ui-parent-card title="Textfield">
        <v-row>
          <v-col cols="12" lg="6">
            <!-- variant -->
            <ui-child-card title="Variant">
              <div>
                <v-text-field color="primary" label="Outlined" placeholder="Placeholder" variant="outlined" />

                <v-text-field color="primary" label="Filled" placeholder="Placeholder" variant="filled" />

                <v-text-field color="primary" label="Underlined" placeholder="Placeholder" variant="underlined" />
              </div>
            </ui-child-card>
          </v-col>
          <v-col cols="12" lg="6">
            <!-- general -->
            <ui-child-card title="General">
              <div>
                <v-text-field color="primary" placeholder="Email Address" variant="outlined" />

                <v-text-field color="primary" placeholder="Email Address" value="demo@company.com" variant="outlined" />

                <v-text-field color="primary" disabled placeholder="demo@company.com" variant="outlined" />
              </div>
            </ui-child-card>
          </v-col>
          <v-col cols="12" lg="6">
            <!-- with caption -->
            <ui-child-card title="With Caption">
              <v-text-field
                v-model="caption_email1"
                color="primary"
                label="Email Address"
                placeholder="email address"
                variant="outlined"
              >
                <template #prepend-inner>
                  <mail-icon size="22" stroke-width="1.5" />
                </template>
              </v-text-field>
              <v-text-field v-model="caption_email2" color="primary" label="Email Address" variant="outlined" />
              <v-text-field v-model="caption_email3" color="primary" label="Email Address" variant="outlined">
                <template #append-inner>
                  <mail-icon size="22" stroke-width="1.5" />
                </template>
              </v-text-field>
            </ui-child-card>
          </v-col>
          <v-col cols="12" lg="6">
            <!-- with validation -->
            <ui-child-card title="With Validation">
              <v-text-field
                v-model="validate_email1"
                color="error"
                error
                label="Email Address"
                placeholder="demo"
                :rules="[rules.required, rules.email]"
                variant="outlined"
              >
                <template #prepend-inner>
                  <mail-icon size="22" stroke-width="1.5" />
                </template>
              </v-text-field>
              <v-text-field
                v-model="validate_email2"
                color="error"
                error
                label="Email Address"
                placeholder="demo"
                :rules="[rules.required, rules.email]"
                variant="outlined"
              />
              <v-text-field color="error" label="Email Address" variant="outlined" />
            </ui-child-card>
          </v-col>
          <v-col cols="12" lg="6">
            <!-- With Icon & Adornments -->
            <ui-child-card title="With Icon & Adornments">
              <v-text-field color="primary" placeholder="Email address" variant="outlined">
                <template #prepend-inner>
                  <mail-icon size="22" stroke-width="1.5" />
                </template>
              </v-text-field>
              <v-text-field color="primary" placeholder="Email address" variant="outlined">
                <template #prepend-inner>
                  <lock-icon size="22" stroke-width="1.5" />
                </template>
                <template #append-inner>
                  <eye-icon size="22" stroke-width="1.5" />
                </template>
              </v-text-field>
              <v-text-field color="primary" placeholder="John Deo" variant="outlined">
                <template #prepend-inner>
                  <span class="v-card-subtitle px-0">Mr</span>
                  <v-divider class="ml-3 my-3 mt-n1" vertical />
                </template>
              </v-text-field>
              <v-text-field color="primary" placeholder="Password" variant="outlined">
                <template #append-inner>
                  <v-divider class="mr-3 my-3 mt-n1" vertical />
                  <span class="v-card-subtitle px-0">.com</span>
                </template>
              </v-text-field>
            </ui-child-card>
          </v-col>
          <v-col cols="12" lg="6">
            <!-- Multiline -->
            <ui-child-card title="Multiline">
              <v-textarea
                auto-grow
                color="primary"
                filled
                label="Multiline Placeholder"
                row-height="20"
                rows="1"
                variant="outlined"
              />
              <v-textarea
                v-model="multiline2"
                auto-grow
                color="primary"
                filled
                label="Multiline Placeholder"
                rows="4"
                variant="outlined"
              />
              <v-textarea
                clear-icon="mdi-close-circle"
                clearable
                color="primary"
                label="Multiline Clearable"
                row-height="20"
                rows="1"
                value="This is clearable text."
                variant="outlined"
              />
            </ui-child-card>
          </v-col>
          <v-col cols="12" lg="6">
            <!-- Select -->
            <ui-child-card title="Select">
              <v-select color="primary" density="comfortable" :items="items" label="Email Address" variant="outlined" />
              <v-select
                v-model="select_sm"
                color="primary"
                density="compact"
                :items="items"
                label="Email Address"
                outlined
                variant="outlined"
              />
            </ui-child-card>
          </v-col>
          <v-col cols="12" lg="6">
            <!-- size -->
            <ui-child-card title="Size">
              <v-text-field color="primary" label="Default" placeholder="Default" variant="outlined" />
              <v-text-field color="primary" density="compact" placeholder="Default" variant="outlined" />
            </ui-child-card>
          </v-col>
          <v-col cols="12">
            <!-- Layout -->
            <ui-child-card title="Layout">
              <v-text-field
                v-model="full_text"
                color="primary"
                hint="Full Width!"
                label="Label"
                persistent-hint
                variant="outlined"
              />
              <v-row class="mt-5">
                <v-col cols="12" lg="4">
                  <v-text-field
                    v-model="some_imp1"
                    color="primary"
                    hint="Some important text"
                    label="None"
                    persistent-hint
                    variant="outlined"
                  />
                </v-col>

                <v-col cols="12" lg="4">
                  <v-text-field
                    v-model="some_imp2"
                    color="primary"
                    density="compact"
                    hint="Some important text"
                    label="Dense"
                    persistent-hint
                    variant="outlined"
                  />
                </v-col>

                <v-col cols="12" lg="4">
                  <v-text-field
                    v-model="some_imp3"
                    color="primary"
                    hint="Some important text"
                    label="Normal"
                    persistent-hint
                    variant="outlined"
                  />
                </v-col>
              </v-row>
            </ui-child-card>
          </v-col>
        </v-row>
      </ui-parent-card>
    </v-col>
  </v-row>
</template>
