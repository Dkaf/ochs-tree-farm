<template>
  <v-app>
    <v-toolbar
      app
      tabs
      color="white"
    >
      <v-tabs
        slot="extension"
        light
        slider-color="green"
        right
      >
        <v-tab
          v-for="(link, i) in links"
          :key="i"
        >
          <nuxt-link :to="link.to">{{ link.title }}</nuxt-link>
        </v-tab>
      </v-tabs>
    </v-toolbar>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer
      :fixed="fixed"
      app
    >
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data() {
      return {
        fixed: false,
        links: [
          { title: 'Home', to: '/' },
          { title: 'About', to: '/about' },
          { title: 'Contact', to: '/contact' }
        ],
        title: 'Ochs Tree Farm'
      }
    }
  }
</script>
