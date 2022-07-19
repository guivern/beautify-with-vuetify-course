<!-- default application markup -->
<!-- https://next.vuetifyjs.com/en/components/application/ -->
<template>
  <v-app>
    <v-app-bar color="primary" dark>
      <v-toolbar-title>Vuetify Dashboard</v-toolbar-title>
      <v-btn rounded>Home</v-btn>
      <v-btn rounded>Login</v-btn>
    </v-app-bar>
    <v-main>
      <v-container fluid>
        <v-card width="400px" class="mx-auto mt-5">
          <v-card-title class="pb-5">
            <h1>Login</h1>
          </v-card-title>
          <v-card-text>
            <v-form>
              <v-text-field
                label="Username"
                prepend-icon="mdi-account-circle"
              ></v-text-field>
              <v-text-field
                label="Password"
                prepend-icon="mdi-lock"
                :type="showPassword ? 'text' : 'password'"
                :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                @click:append="showPassword = !showPassword"
              ></v-text-field>
            </v-form>
          </v-card-text>
          <v-divider></v-divider>
          <v-card-actions>
            <v-btn color="success">Register</v-btn>
            <v-spacer></v-spacer>
            <v-btn color="info">Login</v-btn>
          </v-card-actions>
        </v-card>
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
        >
          {{ link }}
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
    showPassword: false,
    links: ["Home", "Login"],
  }),
};
</script>
