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
          <v-col>
            <h2>Self-introduction:</h2>
            <div style="margin-left: 10px">{{ description }}</div>
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
    profile: require("../assets/profile.jpg"),
    description:
      "新米Androidエンジニアです。SNSアプリやBluetoothで接続されたセンサを制御するアプリを作っています。新しい技術に日々触れながら、常に成長し続けられるエンジニアでありたいと思っています。",
    links: [
      {
        site: "GitHub",
        href: "https://github.com/5altNaCl",
      },
      {
        site: "Qiita",
        href: "https://qiita.com/5alt_NaCl",
      },
      {
        site: "Twitter",
        href: "https://twitter.com/5alt_NaCl",
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
