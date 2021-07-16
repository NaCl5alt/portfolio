<template>
  <v-app-bar absolute color="white" elevate-on-scroll scroll-target=".v-main">
    <v-spacer />
    <v-breadcrumbs :items="items" divider="/" large />
  </v-app-bar>
</template>

<script>
export default {
  name: "Header",

  data: () => ({
    items: [
      {
        text: "Profile",
        disabled: false,
        href: "#",
        exact: true,
      },
      {
        text: "Career",
        disabled: false,
        href: "#",
        exact: true,
      },
      {
        text: "Products",
        disabled: false,
        href: "#",
        exact: true,
      },
    ],
  }),
};
</script>
