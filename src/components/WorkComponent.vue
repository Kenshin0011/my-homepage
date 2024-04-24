<template>
  <div class="work-container" id="works">
    <v-list
        :items="items"
        lines="five"
        item-props
    >
      <template v-slot:title="{ title }">
        <div v-html="title"></div>
      </template>
      <template v-slot:subtitle="{ subtitle }">
        <div v-html="subtitle"></div>
      </template>
    </v-list>
  </div>
</template>

<script>

export default {
  data() {
    return {
      items: [
        {
          title: `<span class="text-bold lg">Works</span>`,
        },
        {
          prependAvatar: './public/images/works/imai-logo.png',
          title: `<br><span class="text-bold lg work-title">今井倫太研究室（2022/2〜現在）</span>`,
          subtitle: `<span class="text-primary md">研究</span>
                    <br>&mdash; LLMを用いて対話において解釈の齟齬が生じるような聞き逃し発話を特定し、日常対話において応用する研究をしている
                    <br>&mdash; CRESTプロジェクトのオンライン体験会に向けシステムを実装中
                    <br>&mdash; 国内学会発表
                    <br>・2024/3/15 <a href="https://www.ipsj.or.jp/event/taikai/86/WEB/data/pdf/2W-01.html">情報処理学会第86回全国大会</a>
                    <br>・2024/5/30 人工知能学会全国大会（第38回）<br><br>`,
        },
        { type: 'divider', inset: true },
        {
          prependAvatar: './public/images/works/sdb_logo.png',
          title: `<br><span class="text-bold lg">ソーシャルデータバンク株式会社（2023/11〜現在）</span>`,
          subtitle: `<span class="text-primary md">長期開発インターン</span>
                    <br>&mdash; 会議室予約・出社管理システム「ワクマネ」のフロント・バックエンドの開発をしている（Vue.js, Laravel）
                    <br>&mdash; 2024/4からRAGを用いたSlackでの質問応答App「ai-manual」のプロジェクトにも参加<br><br>`,
        },
        { type: 'divider', inset: true },
        {
          prependAvatar: './public/images/works/town-logo.jpg',
          title: `<br><span class="text-bold lg">TOWN株式会社（2022/8〜2022/9）</span>`,
          subtitle: `<span class="text-primary md">短期開発インターン</span>
                    <br>&mdash; GoogleMapのAPIを用いて、駐輪場を検索する地図アプリの作成をした（jQuery, CakePHP...）<br><br>`,
        },
        { type: 'divider', inset: true },
      ],
    }
  }
}
</script>

<style scoped>
.work-container {
  padding: 16px;
  background-color: white;
}
</style>
