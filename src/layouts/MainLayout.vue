<template>
  <q-layout view="lHh Lpr lFf" >
    <q-header elevated style="background-color: black;">
      <q-toolbar>
        <q-toolbar-title class="text-center text-3xl">
           Dashboard
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  components: {
  }
})
</script>
