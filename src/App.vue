<template>
  <v-app>
    <v-app-bar
      absolute
      color="teal lighten-3"
      elevate-on-scroll
      scroll-target="#main"
    >
      <v-spacer />
      <v-breadcrumbs :items="items">
        <template v-slot:item="{ item }">
          <a
            href="javascript:void(0)"
            @click="onClickLink(item.href)"
            class="link"
          >
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
  methods: {
    onClickLink(id) {
      document.getElementById(id).scrollIntoView({ behavior: "smooth" });
    },
  },
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
        href: "Profile",
        exact: true,
      },
      {
        text: "Career",
        disabled: false,
        href: "Career",
        exact: true,
      },
      {
        text: "Products",
        disabled: false,
        href: "Products",
        exact: true,
      },
    ],
  }),
};
</script>

<style>
h1 {
  text-shadow: 2px 0px 5px #808080;
}
#Profile,
#Career,
#Products {
  padding: 74px 0px 0px;
}
.link {
  font-size: large;
  color: black !important;
  text-decoration: none;
}
.link:hover {
  font-weight: bold;
}
</style>
