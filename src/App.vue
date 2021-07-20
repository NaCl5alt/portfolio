<template>
  <v-app>
    <v-app-bar absolute color="white" elevate-on-scroll scroll-target="#main">
      <v-spacer />
      <v-breadcrumbs :items="items" large>
        <template v-slot:item="{ item }">
          <a :href="item.href" style="color: black; text-decoration: none">
            {{ item.text }}
          </a>
        </template>
      </v-breadcrumbs>
    </v-app-bar>
    <v-sheet id="main" class="overflow-y-auto" max-height="100vh">
      <v-main style="margin: 0px 10px 0px; position: relative">
        <Profile />
        <Career />
        <Products />
      </v-main>
    </v-sheet>
  </v-app>
</template>

<script>
import Profile from "./components/Profile.vue";
import Career from "./components/Career.vue";
import Products from "./components/Products.vue";

export default {
  name: "App",

  components: {
    Profile,
    Career,
    Products,
  },
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
