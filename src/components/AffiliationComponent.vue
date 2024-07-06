<template>
  <div class="affiliation-container" id="affiliation">
    <div class="text-bold lg">Affiliation</div>
    <v-list v-for="item in items" :key="item" class="lists">
      <div class="icon">
        <img :src="item.prependAvatar" alt="icon" width="60" height="60">
      </div>
      <div class="contents">
        <div class="text-bold lg affiliation-title break">
          {{ item.titleContent }}
        </div>
        <div class="text-primary md">{{ item.subtitle }}</div>
        <div v-for="(line, index) in item.content" :key="index">
          <div>&mdash; {{ line.text }}</div>
        </div>
        <div v-if="item.conference" class="conference">
          <div v-for="(line, index) in item.conference" :key="index" class="conference-list">
            <span v-if="!line.link"> {{ line.text }}</span>
            <a v-else :href="line.link" class="link">{{ line.text }}</a>
          </div>
        </div>
      </div>
    </v-list>
  </div>
</template>


<script>
export default {
  data() {
    return {
      items: [
        {
          prependAvatar: './images/affiliation/imai-logo.png',
          titleContent: "今井倫太研究室（2023/2月〜現在）",
          subtitle: "研究",
          content: [
            { text: "LLMを用いて対話において解釈の齟齬が生じるような聞き逃し発話を特定し、日常対話において応用する研究をしている" },
            { text: "CRESTプロジェクトのオンライン体験会に向けシステムを実装中" },
            { text: "国内学会発表" },
          ],
          conference: [
            { text: "・2024/3/15" },
            { text: "情報処理学会第86回全国大会", link: "https://www.ipsj.or.jp/event/taikai/86/WEB/data/pdf/2W-01.html" },
            { text: "・2024/5/30" },
            { text: "人工知能学会全国大会（第38回）", link: "https://www.jstage.jst.go.jp/article/pjsai/JSAI2024/0/JSAI2024_3T1OS6a02/_pdf/-char/ja"},
          ]
        },
        {
          prependAvatar: './images/affiliation/sdb_logo.png',
          titleContent: "ソーシャルデータバンク株式会社（2023/11月〜現在）",
          subtitle: "長期開発インターンシップ",
          content: [
            { text: "会議室予約・出社管理システム「ワクマネ」のフロント・バックエンドの開発をしている（Vue.js, Laravel）" },
            { text: "2024/7月からジャズピアノの音ゲーアプリJazz-Stepsの開発をしている（Nuxt.js, Laravel）" },
          ],
        },
        {
          prependAvatar: './images/affiliation/town-logo.jpg',
          titleContent: "TOWN株式会社（2022/9月の数日間）",
          subtitle: "短期開発インターンシップ",
          content: [
            { text: "GoogleMapのAPIを用いて、駐輪場を検索する地図アプリの作成をした（jQuery, CakePHP...）" },
          ],
        },
      ],
    }
  },
}
</script>

<style scoped>
.affiliation-container {
  padding: 90px 32px;
  background-color: white;
}

.break {
  width: 100%; /* 適切な幅の設定 */
  word-break: break-all;
  overflow-wrap: break-word;
}

.lists {
  display: flex;
  flex-direction: row;
  border-bottom: 1px solid var(--vt-c-divider-dark-2);
}

.icon {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 20px;
}

.contents {
  padding: 24px;
}

.conference {
  padding-left: 16px;
}
</style>
