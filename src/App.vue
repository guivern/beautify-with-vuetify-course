<template>
  <v-app>
    <v-app-bar color="primary" dark>
      <v-toolbar-title>Vuetify Dashboard</v-toolbar-title>
      <v-btn v-for="link in links" :key="link" rounded :to="link.url"
        >{{ link.label }}
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container fluid>
        <router-view></router-view>
      </v-container>
    </v-main>
    <v-footer color="primary" app>
      <v-row justify="center" no-gutters>
        <v-btn
          v-for="link in links"
          :key="link"
          color="white"
          variant="text"
          class="mx-2"
          rounded="xl"
          :to="link.url"
        >
          {{ link.label }}
        </v-btn>
        <v-col class="text-center text-white mt-4" cols="12">
          {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},

  data: () => ({
    links: [
      { label: "Home", url: "/" },
      { label: "Login", url: "/login" },
      { label: "Dahsboard", url: "/dashboard" },
    ],
  }),
};
</script>
