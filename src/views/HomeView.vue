<template>
  <v-app>
    <header-p />
    <hopcoes />
    <v-col cols="12">
      <home-page />
    </v-col>
    <footerV />
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue'
import HomePage from '../components/HomePage.vue'
import HeaderP from '../components/HeaderPrincipal.vue'
import Hopcoes from '../components/HeaderOpções.vue'
import footerV from '../components/FooterVue.vue'
export default Vue.extend({

  components: {
    footerV,
    Hopcoes,
    HomePage,
    HeaderP,
  },
  name: 'home-view',

  data() {

    return {
      user: 'Renan Andrade',

      searchInput: '',
      links: [
        { name: 'Página Inicial', route: '/home' },
        { name: 'Ajuda', route: '/help' },
      ],
    }
  },
  methods: {

    logout() {
      // Lógica para efetuar o logout
      // Redirecionar para a rota de login
      this.$router.push('./');
    },
    goToRoute(route: string) {
      const selectedLink = this.links.find((item: any) => item.name === route);
      if (selectedLink) {
        this.$router.push(selectedLink.route);
      }
    }
  }




})
</script>

<style scoped>
.title {
  font-family: 'Sora', sans-serif;
}

.menu-item {
  font-family: 'Sora', sans-serif;
}

.mp-10 {
  margin-top: 10px;
}
</style>
