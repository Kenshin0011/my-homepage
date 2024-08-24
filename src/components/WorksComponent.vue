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

                    <v-card-subtitle class="pt-4">{{ card.where }}</v-card-subtitle>

                    <v-card-text>
                    <ul class="card-message sm">
                        <li v-for="(line, index) in formattedMessage(card.content)" :key="index">
                            <template v-for="(part, partIndex) in line.parts" :key="partIndex">
                                <span v-if="part.type === 'text'" v-text="part.text"></span>
                            </template>
                        </li>
                    </ul>
                    </v-card-text>
                    <a v-if="card.title === 'ワクマネ'" href="https://zenn.dev/kenshin0011/articles">
                        <img src="https://zenn.badge.nikaera.com/s/kenshin0011/articles?style=plastic" alt="kenshin0011 articles" />
                    </a>
                    <a v-if="card.title === 'Jazz-Steps'" href="https://jazz-steps.com/">
                      https://jazz-steps.com/
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
                    img: 'wakumane.png',
                    title: 'ワクマネ',
                    where: '長期インターンシップ',
                    content: 'Vue.jsとLaravelで開発\n' +
                        'ソーシャルデータバンク株式会社のプロダクトの１つ\n' +
                        '開発以外にもコードレビューや機能提案からの実装など幅広く担当し、Zennの執筆＋勉強会も開催した\n' +
                        '単体・機能テストやN+1問題など苦労した点もあったが、入社日以降メンバーの中で一番コードを書いたこともあり、成果発表会で過去最高点でMVPを受賞',
                },
                {
                    img: 'jazz.png',
                    title: 'Jazz-Steps',
                    where: '長期インターンシップ',
                    content: '株式会社 Freedom Freaksのプロダクト\n' +
                        'Nuxt.jsとLaravel\n' +
                        'フロント：アトミックデザイン\n' +
                        'バック：ドメイン駆動設計とオニオンアーキテクチャ\n' +
                        '社員にレビューしてもらうために押し入り参加'
                },
                {
                  img: 'chat_ui.png',
                  title: 'チャットApp',
                  where: '研究室',
                  content: '外部の方々に対して研究のオンライン体験会を行うために作成したZoom形式のチャットApp\n' +
                    'React×FastAPI×PostgreSQL×Dockerで作成\n' +
                    'GithubPages×Renderでデプロイ\n' +
                    'ログインや対話履歴の保持のためにDBを使用\n' +
                    'i18nによる多言語対応\n' +
                    '01で実装する力が身についた',
                  github: 'https://github.com/imai-laboratory/SCAINs_pseudo_chat',
                },
                {
                    img: 'screw.png',
                    title: '英文トレーニング',
                    where: '研究室（新人研修）',
                    content: '研究室に入った時に作った英語力を鍛えるシステム\n' +
                        'flaskで作成\n' +
                        '4択問題演習、英文トレーニング、ランダム単語バトルの3モードある\n' +
                        'flask-sqlalchemyで管理しており、ユーザのランキングも競える',
                },
                {
                  img: 'kagu.png',
                  title: '家具レンタルシステム',
                  where: '個人開発',
                  content: 'Javaのみで作成\n' +
                    '制作期間：約2週間\n' +
                    '1人で2000行程度のコードを書いたため、自信に繋がった初めてのシステム',
                  github: 'https://github.com/Kenshin0011/Probfinal',
                },
                {
                  img: 'portfolio.png',
                  title: 'ポートフォリオ',
                  where: '個人開発',
                  content: 'Vue.js×Dockerで作成\n' +
                    '制作期間：約3日間\n' +
                    'htmlでも良かったが、0からVueプロジェクトを作ってみたかった\n' +
                    'Vuetifyを使ってスタイルを整えたかったことも要因の１つ',
                  github: 'https://github.com/Kenshin0011/my-homepage',
                },
            ],
        }
    },
    methods: {
        formattedMessage(message) {
            return message.split('\n').map(line => {
                const parts = []; // この配列を使ってテキストを分割する
                parts.push({ type: 'text', text: line }); // すべての行をテキストとして扱う
                return { parts };
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
