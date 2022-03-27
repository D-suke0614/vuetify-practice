<template>
  <v-app>
    <v-app-bar class="bg-cyan-darken-1 text-white">
      <v-app-bar-nav-icon variant="text" @click="drawer = !drawer"/>
      <v-toolbar-title>Vuetify Practice</v-toolbar-title>
      <v-space></v-space>
      <v-btn variant="text" icon="mdi-magnify"></v-btn>
      <v-btn variant="text" icon="mdi-filter"></v-btn>
      <v-btn variant="text" icon="mdi-dots-vartical"></v-btn>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" temporary>
      <v-list :items="items"></v-list>
    </v-navigation-drawer>

    <v-main>
      <HelloWorld/>
    </v-main>

    <v-footer class="bg-cyan-darken-1">
      <v-row justify="center">
        <v-btn v-for="item in items" :key="item" color="white" variant="text">
          {{ item.title }}
        </v-btn>
        <v-col class="text-center text-white" cols="12">
          {{ new Date().getFullYear() }} - <strong>Vuetify Practice</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',

  components: {
    HelloWorld,
  },

  data: () => ({
    drawer: null,
    items: [
      { title: 'ホーム', value: 'home' },
      { title: '会社概要', value: 'companyr' },
      { title: 'サービス', value: 'service' },
      { title: 'お問い合わせ', value: 'inquiry' },
    ]
  }),
}
</script>
