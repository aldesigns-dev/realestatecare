<template>
  <nav>
    <v-app-bar :elevation="3">
      <v-app-bar-nav-icon color="rec-primary" @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-spacer></v-spacer>
      <img :src="require('@/assets/rec-logo-icon-left.png')" alt="Real Estate Care logo" class="rec-logo">
      <!-- <router-link to="/">
        <img :src="require('@/assets/rec-logo-icon-left.png')" alt="Real Estate Care logo" class="rec-logo">
      </router-link> -->
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon color="rec-primary">mdi-account</v-icon>
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" app temporary>
      <v-list>
        <v-list-item  v-for="item in menuItems" :key="item.text" router :to="item.route">
          <v-list-item-title><v-icon>{{ item.icon }}</v-icon>{{ item.text }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
export default {
  name: 'NavBar',
  data() {
    return {
      drawer: false,
      menuItems: [
        { icon: 'mdi-home', text: 'Dashboard', route: '/' },
        { icon: 'mdi-file-outline', text: 'Toegewezen rapportages', route: '/toegewezen-rapportages' },
        { icon: 'mdi-file-check-outline', text: 'Uitgevoerde rapportages', route: '/uitgevoerde-rapportages' },
        { icon: 'mdi-text-box-search-outline', text: 'Documentatie', route: '/documentatie' },
        { icon: 'mdi-cog', text: 'Instellingen', route: '/instellingen' },
      ]
    };
  }
}
</script>

<style scoped>
.rec-logo {
  width: 100%;
  max-width: 150px;
}
.v-list-item--active > .v-list-item__overlay {
  opacity: 0;
}
</style>