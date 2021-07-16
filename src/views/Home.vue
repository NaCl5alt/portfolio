<template>
  <div>
    <Profile />
    <Career />
    <Products />
  </div>
</template>

<script>
import Profile from "../components/Profile.vue";
import Career from "../components/Career.vue";
import Products from "../components/Products.vue";

export default {
  name: "Home",

  components: {
    Profile,
    Career,
    Products,
  },
};
</script>
