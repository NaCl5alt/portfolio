<template>
  <v-container fluid id="Career">
    <v-layout wrap fill-height style="display: block">
      <h1>Career</h1>
      <v-card tile elevation="5">
        <v-row
          style="margin: 10px 10px 0px; padding-bottom: 10px"
          v-for="item in career"
          :key="item.text"
        >
          <div style="margin: 10px 10px 0px">
            {{ item.date }}: {{ item.text }}
          </div>
        </v-row>
      </v-card>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: "Career",
  data: () => ({
    career: [
      {
        date: "2016/04",
        text: "東京都立産業技術高等専門学校 ものづくり工学科入学",
      },
      {
        date: "2017/10",
        text: "全国高等専門学校第28回プログラミングコンテスト 課題部門 本選出場",
      },
      {
        date: "2018/08",
        text: "第24回スーパーコンピューティングコンテスト SuperCon2018 本選出場",
      },
      {
        date: "2019/11",
        text: "基本情報技術者試験 取得",
      },
      {
        date: "2019/11",
        text: "Internet Week 2019 NOCチーム",
      },
      {
        date: "2020/11",
        text: "株式会社レボーン モバイル開発チーム アルバイト入社",
      },
      {
        date: "2021/03",
        text: "東京都立産業技術高等専門学校 ものづくり工学科卒業",
      },
      {
        date: "2021/04",
        text: "東京都立産業技術高等専門学校 創造工学専攻 情報工学コース入学",
      },
      {
        date: "2021/08",
        text: "チームラボ株式会社 スマホアプリエンジニア インターンシップ",
      },
      {
        date: "2021/09/30",
        text: "東京都立産業技術高等専門学校 創造工学専攻 情報工学コース退学",
      },
      {
        date: "2022/01/01",
        text: "株式会社レボーン 商品開発部 開発課 入社",
      },
      {
        date: "2022/12",
        text: "応用情報技術者試験 取得",
      },
    ],
  }),
};
</script>
