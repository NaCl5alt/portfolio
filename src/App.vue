<template>
  <v-app>
    <v-card class="overflow-hidden">
      <v-app-bar absolute color="white" elevate-on-scroll scroll-target="#main">
        <v-spacer />
        <v-breadcrumbs :items="items" />
      </v-app-bar>
      <v-sheet id="main" class="overflow-y-auto" max-height="100vh">
        <v-main style="position: relative">
          <router-view />
        </v-main>
      </v-sheet>
    </v-card>
  </v-app>
</template>

<script>
export default {
  name: "App",

  components: {},
  data: () => ({
    items: [
      {
        text: "Profile",
        disabled: false,
        href: "#Profile",
        exact: true,
      },
      {
        text: "Career",
        disabled: false,
        href: "#Career",
        exact: true,
      },
      {
        text: "Products",
        disabled: false,
        href: "#Products",
        exact: true,
      },
    ],
  }),
};
</script>
