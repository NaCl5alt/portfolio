<template>
  <v-container fluid id="Profile">
    <v-layout wrap fill-height style="display: block">
      <h1>Profile</h1>
      <v-card tile elevation="5">
        <v-row style="margin: 10px 10px 0px">
          <v-dialog
            v-model="dialog"
            max-width="500"
            align="center"
            align-content="center"
          >
            <template v-slot:activator="{ on, attrs }">
              <v-avatar
                size="150"
                v-on="on"
                v-bind="attrs"
                style="margin: 25px"
              >
                <img :src="profile" alt="profileImg" />
              </v-avatar>
            </template>
            <v-card>
              <img :src="profile" alt="profileImg" width="500" />
            </v-card>
          </v-dialog>
          <v-col>
            <div><b>Name:</b> {{ name }}</div>
            <div><b>Birthday(age):</b> {{ birthDay }} ({{ calcAge }})</div>
            <div>
              <b>Link:</b><br />
              <ul>
                <li v-for="link in links" :key="link.site">
                  <a :href="link.href">{{ link.site }}</a>
                </li>
              </ul>
            </div>
          </v-col>
          <v-col sm="12" md="7">
            <h2>Self-introduction:</h2>
            <p class="ml-2 text-pre-wrap">{{ description }}</p>
          </v-col>
        </v-row>
      </v-card>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: "Profile",
  data: () => ({
    name: "斎木翔太",
    birthDay: "2001/02/10",
    profile: require("../assets/profile.png"),
    description:
      "Androidアプリ開発を始め、フロントエンド・バックエンド、インフラ構築運用をやったりするなんでも屋さんです。(気持ちはモバイルアプリエンジニアですが)\nSNSアプリや、Bluetooth・USBで接続されたにおいセンサやUSBで接続されたディフューザーを制御するアプリを開発しています。\n新しい技術に日々触れながら、常に成長し続けられるエンジニアでありたいと思っています。",
    links: [
      {
        site: "GitHub",
        href: "https://github.com/NaCl5alt",
      },
      {
        site: "Qiita",
        href: "https://qiita.com/NaCl_5alt",
      },
      {
        site: "X(旧Twitter)",
        href: "https://x.com/NaCl_5alt",
      },
      {
        site: "Wantedly",
        href: "https://www.wantedly.com/id/NaCl_5alt",
      },
    ],
    dialog: false,
  }),
  computed: {
    calcAge() {
      let birthdate = this.birthDay.replace(/[/-]/g, "");
      let today = new Date();
      let targetdate =
        today.getFullYear() * 10000 +
        (today.getMonth() + 1) * 100 +
        today.getDate();
      return Math.floor((targetdate - birthdate) / 10000);
    },
  },
};
</script>
