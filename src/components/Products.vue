<template>
  <v-container fluid style="height: 100vh; padding: 65px 0px 0px" id="Products">
    <v-layout wrap fill-height style="display: block">
      <h1>Products</h1>
      <v-row style="margin: 10px 10px 0px">
        <v-col>
          <div v-for="product in products" :key="product.name">
            <v-dialog v-model="dialog" max-width="400">
              <template v-slot:activator="{ on, attrs }">
                <v-row
                  v-on="on"
                  v-bind="attrs"
                  align="center"
                  style="cursor: pointer; margin-top: 10px"
                  :title="product.name"
                >
                  <v-avatar size="72">
                    <img :src="product.logo" alt="profileImg" />
                  </v-avatar>
                  <h2 style="margin-left: 10px">{{ product.name }}</h2>
                </v-row>
              </template>
              <v-card
                align="center"
                align-content="center"
                style="padding: 10px"
              >
                <div style="font-size: large; margin: 10px">
                  GooglePlayStoreへ移動しますか？
                </div>
                <v-card-actions>
                  <v-spacer />
                  <v-btn color="primary" text @click="onClickLink(product.link)"
                    >はい</v-btn
                  >
                </v-card-actions>
              </v-card>
            </v-dialog>
            <v-row style="margin: 30px 10px 0px">
              <div style="margin: 10px 0px 20px">
                {{ product.description }}
              </div>
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
export default {
  name: "Products",
  data: () => ({
    dialog: false,
    products: [
      {
        name: "Piperia - 学生専用SNS（ピペリア）",
        description: "全ての学生にオープンな場所を提供する学生専用SNS",
        logo: require("../assets/piperia/logo.png"),
        link: "https://play.google.com/store/apps/details?id=net.piperia.android",
        images: [
          {
            alt: "PiperiaFeature",
            href: require("../assets/piperia/feature.png"),
          },
          {
            alt: "PiperiaHome",
            href: require("../assets/piperia/home.png"),
          },
          {
            alt: "PiperiaCommunity",
            href: require("../assets/piperia/community.png"),
          },
          {
            alt: "PiperiaDM",
            href: require("../assets/piperia/dm.png"),
          },
        ],
      },
    ],
  }),
  methods: {
    onClickLink(link) {
      this.dialog = false;
      window.open(link, "_blank");
    },
  },
};
</script>
