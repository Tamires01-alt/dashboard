<template>
  <q-layout view="lHh Lpr lFf" >
    <q-header elevated style="background-color: black;">
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />
        <q-toolbar-title>
          Quasar App
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list
      >
        <q-item-label
          header
        >
          Dashboard
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'
const linksList = [
  {
    title: 'Pages',
    caption: 'quasar.dev',
    icon: 'fa-solid fa-pager',
    link: 'https://quasar.dev'
  },
  {
    title: 'Maps',
    caption: 'github.com/quasarframework',
    icon: 'fa-solid fa-map',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Mail',
    caption: 'chat.quasar.dev',
    icon: 'fa-solid fa-envelope',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Menu levels',
    caption: 'forum.quasar.dev',
    icon: 'fa-solid fa-bars',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Tree Table',
    caption: '@quasarframework',
    icon: 'fa-solid fa-list',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Charts',
    caption: '@QuasarFramework',
    icon: 'fa-solid fa-chart-simple',
    link: 'https://facebook.quasar.dev'
  }
]

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
