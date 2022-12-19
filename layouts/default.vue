<template>
  <div>
    <v-app>
      <v-content>
        <v-toolbar>
          <v-toolbar-side-icon></v-toolbar-side-icon>
          <v-toolbar-title>Nuxt Practice</v-toolbar-title>
          <v-spacer></v-spacer>
          <v-toolbar-items class="hidden-sm-and-down">
            <v-btn>
              <n-link to="/weather-app">Weather App</n-link>
            </v-btn>
          </v-toolbar-items>
        </v-toolbar>

        <transition>
          <v-content>
            <nuxt />
          </v-content>
        </transition>
      </v-content>
    </v-app>
  </div>
</template>

<script>
export default {
  data() {
    return {
      toggle: false
    };
  }
};
</script>

<style>
a {
  text-decoration: none;
}
</style>