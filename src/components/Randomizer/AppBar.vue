<template>
  <v-app-bar
    app
    color="blue darken-2"
    dark
  >
    <v-app-bar-nav-icon @click.stop="$emit('toggleDrawer')" />
    <v-toolbar-title>
      <v-btn class="ma-2" color="white" x-large icon link href="https://riwert.github.io/v-randomizer">
        <v-icon>mdi-vuetify</v-icon>
      </v-btn>
      <slot />
    </v-toolbar-title>
  </v-app-bar>
</template>

<script>
export default {
  name: 'AppBar'
}
</script>
