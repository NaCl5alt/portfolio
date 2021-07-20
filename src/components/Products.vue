<template>
  <v-container fluid style="height: 100vh; padding: 65px 0px 0px" id="Products">
    <v-layout wrap fill-height style="display: block">
      <h1>Products</h1>
      <v-row style="margin: 10px 10px 0px">
        <v-col>
          <div v-for="product in products" :key="product.name">
            <v-row
              align="center"
              @click="onClickLink(product.link)"
              style="cursor: pointer; margin-top: 10px"
              :title="product.name"
            >
              <v-avatar size="72">
                <img :src="product.logo" alt="profileImg" />
              </v-avatar>
              <h2 style="margin-left: 10px">{{ product.name }}</h2>
            </v-row>
            <v-row style="margin: 30px 10px 0px">
              {{ product.description }}
              <v-carousel
                height="400"
                cycle
                hide-delimiters
                show-arrows-on-hover
              >
                <v-carousel-item v-for="(img, i) in product.images" :key="i">
                  <v-img
                    :src="img.href"
                    :alt="img.alt"
                    contain
                    max-height="400"
                  />
                </v-carousel-item>
              </v-carousel>
            </v-row>
          </div>
        </v-col>
      </v-row>
    </v-layout>
  </v-container>
</template>

<script>
// import piperiaLogo from "../assets/piperia/logo.png";
// import piperiaFeature from "../assets/piperia/feature.png";
// import piperiaHome from "../assets/piperia/home.png";
// import piperiaCommunity from "../assets/piperia/community.png";
// import piperiaDM from "../assets/piperia/dm.png";

export default {
  name: "Products",
  data: () => ({
    products: [
      {
        name: "Sample",
        description: "SampleText",
        logo: "Sample",
        link: "SampleText",
        images: [
          {
            alt: "Sample1",
            href: require("../assets/logo.png"),
          },
          {
            alt: "Sample2",
            href: require("../assets/logo.png"),
          },
        ],
      },
      // {
      //   name: "Piperia - 学生専用SNS（ピペリア）",
      //   description: "全ての学生にオープンな場所を提供する学生専用SNS",
      //   logo: piperiaLogo,
      //   link: "https://play.google.com/store/apps/details?id=net.piperia.android",
      //   images: [
      //     {
      //       alt: "PiperiaFeature",
      //       href: piperiaFeature,
      //     },
      //     {
      //       alt: "PiperiaHome",
      //       href: piperiaHome,
      //     },
      //     {
      //       alt: "PiperiaCommunity",
      //       href: piperiaCommunity,
      //     },
      //     {
      //       alt: "PiperiaDM",
      //       href: piperiaDM,
      //     },
      //   ],
      // },
    ],
  }),
  methods: {
    onClickLink(link) {
      window.open(link, "_blank");
    },
  },
};
</script>
