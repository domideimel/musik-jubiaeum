<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-red-8 text-white" height-hint="98">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo/svg/quasar-logo.svg">
          </q-avatar>
        </q-toolbar-title>
        <q-space />
        <q-btn-toggle
          v-if="!isMobile"
          v-model="model"
          flat stretch
          toggle-color="yellow"
          :options="navigation"
        />
        <q-btn v-if="isMobile" flat @click="drawerLeft = !drawerLeft" round dense icon="menu" />
      </q-toolbar>
    </q-header>
    <q-drawer
      v-if="isMobile"
      v-model="drawerLeft"
      :width="280"
      :breakpoint="500"
      bordered
      content-class="bg-grey-3"
    >
      <q-list class="q-mt-sm">
        <q-item v-for="(menuItem, index) in navigation" :key="index" clickable v-ripple>
          <q-item-section>
            {{ menuItem.label }}
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>
    <q-page-container>
      <router-view />
    </q-page-container>
    <q-footer class="bg-red-8 text-center q-py-sm footer">
      <a class="text-white q-mr-sm" href="https://www.negertalmusikanten.de/about/" target="_blank">Impressum</a>
      <a class="text-white" href="https://www.negertalmusikanten.de/j/privacy" target="_blank">Datenschutz</a>
    </q-footer>
  </q-layout>
</template>

<script>

export default {
  name: 'MainLayout',
  data () {
    return {
      drawerLeft: false,
      model: null,
      navigation: [{
        label: 'Home',
        value: 'home'
      }, {
        label: 'Festjahr',
        value: 'festjahr'
      }, {
        label: 'Chronik',
        value: 'chronik'
      }, {
        label: 'Anmeldung',
        value: 'anmeldung'
      }]
    }
  },
  computed: {
    isMobile () {
      return this.$q.screen.lt.md
    }
  }
}
</script>

<style scoped lang="sass">
  .q-toolbar
    min-height: 80px !important
  .footer
    position: relative !important
</style>
