<template>
  <v-navigation-drawer
    v-model="localDrawer"
    app
    temporary
    dark
    :src="background"
  >
    <AppBar @toggleDrawer="drawer = !drawer">Rndr</AppBar>

    <v-btn class="nav-logo" link href="https://riwert.github.io/v-randomizer">
      <v-img :src="logo" alt="Vuetify Logo" aspect-ratio="1"></v-img>
    </v-btn>

    <v-list dense>
      <v-list-item link href="https://riwert.github.io/v-randomizer">
        <v-list-item-action>
          <v-icon>mdi-home</v-icon>
        </v-list-item-action>
        <v-list-item-content>
          <v-list-item-title>Home</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
      <v-list-item link href="mailto:revert@revert.pl">
        <v-list-item-action>
          <v-icon>mdi-mail</v-icon>
        </v-list-item-action>
        <v-list-item-content>
          <v-list-item-title>Contact</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
      <v-list-item link href="https://github.com/riwert/v-randomizer" target="_blank" rel="noopener">
        <v-list-item-action>
          <v-icon>mdi-github</v-icon>
        </v-list-item-action>
        <v-list-item-content>
          <v-list-item-title>GitHub</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
import AppBar from '@/components/Randomizer/AppBar'
import logo from '@/assets/vuetify-logo.png'
import background from '@/assets/v-bg.webp'

export default {
  name: 'Navigation',

  props: {
    drawer: Boolean
  },

  components: {
    AppBar,
  },

  data: () => ({
    localDrawer: false,
    logo,
    background
  }),

  watch: {
    drawer: function () {
      this.localDrawer = this.drawer
    },
    localDrawer: function () {
      this.$emit('updateDrawer', this.localDrawer)
    }
  }
}
</script>

<style scoped>
.nav-logo {
  display: block;
  max-width: 50%;
  margin-top: 5rem;
  margin-left: auto;
  margin-right: auto;
  padding: 0 !important;
  height: auto !important;
  background: transparent !important;
  box-shadow: none !important;
}
</style>
