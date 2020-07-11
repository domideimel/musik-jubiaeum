<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-red-8 text-white" height-hint="98">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo/svg/quasar-logo.svg">
          </q-avatar>
          Negertalmusikanten
        </q-toolbar-title>
        <q-space />
        <q-btn-toggle
          v-model="model"
          flat stretch
          toggle-color="yellow"
          :options="navigation"
        />
      </q-toolbar>
    </q-header>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>

export default {
  name: 'MainLayout',
  data () {
    return {
      model: null,
      navigation: [{
        label: 'Home',
        value: 'home'
      }, {
        label: 'Festablauf',
        value: 'festablauf'
      }, {
        label: 'Chronik',
        value: 'chronik'
      }, {
        label: 'Anmeldung',
        value: 'anmeldung'
      }]
    }
  }
}
</script>

<style scoped lang="sass">
  .q-toolbar
    min-height: 80px !important
</style>
