<template>
  <v-container fluid style="padding: 64px 0px 0px" id="Profile">
    <v-layout wrap fill-height style="display: block">
      <h1>Profile</h1>
      <v-row
        align="center"
        align-content="center"
        style="margin: 10px 10px 0px"
      >
        <v-avatar size="72">
          <img :src="profile" alt="profileImg" />
        </v-avatar>
        <v-col>
          <div><b>Name:</b> 斎木翔太</div>
          <div><b>Birthday(age):</b> 2001/02/10 (20)</div>
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
          <div style="margin-left: 10px">
            新米Androidエンジニアです。<br />SNSアプリやBluetoothで接続されたセンサを制御するアプリを作ってきました。<br />新しい技術に日々触れながら、常に成長し続けられるエンジニアでありたいと思っています。
          </div>
        </v-col>
      </v-row>
    </v-layout>
  </v-container>
</template>

<script>
import Profile from "../assets/profile.jpg";
export default {
  name: "Profile",
  data: () => ({
    profile: Profile,
    links: [
      {
        site: "GitHub",
        href: "https://github.com/shouta02jp",
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
  }),
};
</script>
