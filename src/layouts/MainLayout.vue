<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>

        <q-btn
          v-if="$route.fullPath.includes('/chat')"
          v-go-back.single
          icon="arrow_back"
          flat
          dense
          label="Back" />

        <q-toolbar-title class="absolute-center">
          {{ title }}
        </q-toolbar-title>

        <q-btn
          to="/"
          class="absolute-right q-pr-sm"
          icon="account_circle"
          no-caps
          flat
          dense
          label="Logout" />

      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { openURL } from 'quasar'

export default {
  computed: {
    title() {
      console.log(this.$route)
      let currentPath = this.$route.fullPath
      if (currentPath == '/home') return 'DataSpell Home Page'
      else if (currentPath == '/chat') return 'Chat'
      else if (currentPath == '/') return 'Login'
    }
  },
  methods: {
    openURL
  }
}
</script>

<style>
</style>
