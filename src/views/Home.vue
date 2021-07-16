<template>
  <div>
    <Header />
    <Profile />
    <Career />
    <Products />
  </div>
</template>

<script>
import Header from "../components/Header.vue";
import Profile from "../components/Profile.vue";
import Career from "../components/Career.vue";
import Products from "../components/Products.vue";

export default {
  name: "Home",

  components: {
    Header,
    Profile,
    Career,
    Products
  },
};
</script>
