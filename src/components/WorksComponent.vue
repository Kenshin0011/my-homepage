<template>
  <div class="works-container" id="works">
    <div class="title text-bold lg">Works</div>
    <div class="works-list">
      <div v-for="(card, i) in cards" :key="i" class="works-item" :class="{ 'mobile-works-list': isMobileScreen }">
        <v-card
            class="mx-auto"
            max-width="400"
            style="padding: 12px;"
        >
          <v-img
              class="align-end text-white"
              height="200"
              :src="`./images/works/${card.img}`"
              cover
          >
            <v-card-title><p class="xl text-bold" style="color: black;">{{ card.title }}</p></v-card-title>
          </v-img>

          <v-card-subtitle class="pt-4">
            {{ card.where }}
          </v-card-subtitle>

          <v-card-text>
            <ul class="card-message sm">
              <li v-for="(item, index) in formattedMessage(card.content)" :key="index" v-html="item"></li>
            </ul>
          </v-card-text>

          <a v-if="card.title === 'ワクマネ'" href="https://zenn.dev/kenshin0011/articles">
            <img src="https://zenn.badge.nikaera.com/s/kenshin0011/articles?style=plastic" alt="kenshin0011 articles" />
          </a>

          <v-card-subtitle v-if="card.github" class="pt-4" style="padding-bottom: 8px">
            <v-btn
                icon="mdi-github"
                :href="card.github"
            ></v-btn>
          </v-card-subtitle>
        </v-card>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  props: {
    isMobileScreen: { type: Boolean, required: true },
  },
  data () {
    return {
      cards: [
        {
          img: 'kagu.png',
          title: '家具レンタルシステム',
          where: '授業',
          content: 'Javaのみで作成\n' +
              '制作期間：約2週間\n' +
              '1人で2000行程度のコードを書いたため、自信に繋がった初めてのシステム',
          github: 'https://github.com/Kenshin0011/Probfinal',
        },
        {
          img: 'wakumane.png',
          title: 'ワクマネ',
          where: '長期インターンシップ',
          content: 'Vue.jsとLaravelで開発\n' +
              'ソーシャルデータバンク株式会社のプロダクトの１つ\n' +
              '開発以外にもコードレビューや機能提案からの実装など幅広く担当し、Zennの執筆＋勉強会も開催した\n' +
              '単体・機能テストやN+1問題など苦労した点もあったが、入社日以降メンバーの中で一番コードを書いたこともあり、成果発表会で過去最高点でMVPを受賞',
        },
        {
          img: 'portfolio.png',
          title: 'ポートフォリオ',
          where: '個人開発',
          content: 'Vue.jsで作成\n' +
              '制作期間：約3日間\n' +
              'htmlでも良かったが、0からVueプロジェクトを作ってみたかった\n' +
              'Vuetifyを使ってスタイルを整えたかったことも要因の１つ',
          github: 'https://github.com/Kenshin0011/my-homepage',
        },
        {
          img: 'ai-manual.png',
          title: 'ai-manual',
          where: '長期インターンシップ',
          content: 'RAGを用いたSlackでの質問応答App\n' +
              'ソーシャルデータバンク株式会社のプロダクトの1つ\n' +
              'Slack APIやRAGの性能に関する調査をやっていく予定',
        },
      ],
    }
  },
  methods: {
    formattedMessage(message) {
      // 各行を改行で分割し、複数の置き換えを行う
      return message.split('\n').map(line => {
        return line;
      });
    }
  }
}
</script>

<style scoped>
.works-container {
  padding: 90px 32px;
}

.works-list {
  display: flex;
  flex-wrap: wrap;
  padding-top: 16px;
  margin-bottom: -40px;
  width: 100%;
}

.mobile-works-list {
  flex-basis: 100%;
}

.works-item {
  width: 31.74603%;
  margin-right: 1.58730%;
  margin-bottom: 40px;
  color: #333;
}

.works-item:hover {
  opacity: .9;
}

.works-item:nth-of-type(3n) {
  margin-right: 0;
}

.works-img img {
  border: 1px solid #e6e6e6;
}
</style>
