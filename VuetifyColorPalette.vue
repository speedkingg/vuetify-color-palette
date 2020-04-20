<template>
  <div>
    <v-card
      v-for="(theme, themeName) in themes"
      :key="themeName"
      :dark="themeName === 'dark'"
      :light="themeName === 'light'"
      class="d-flex pa-5"
    >
      <v-card-title class="mr-5">{{ themeName }}</v-card-title>

      <div v-for="(color, key) in theme" :key="key" class="ma-4">
        <v-card :color="color" height="100px" width="100px" shaped />
        <div class="mt-1 ml-1">{{ key }}</div>
      </div>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "VuetifyColorPalette",
  computed: {
    themes() {
      return this.$vuetify.theme.themes;
    }
  }
};
</script>
