<template>
  <div class="about-container" id="about">
    <div class="info">
        <v-card class="card">
          <v-toolbar color="transparent">
            <v-toolbar-title class="title" text="About"/>
          </v-toolbar>
          <div class="card-body">
            <v-card-text class="card-text">
              <v-timeline align="start" density="compact">
                <v-timeline-item
                    v-for="message in messages"
                    :key="message.year"
                    :dot-color="message.color"
                    size="x-small"
                >
                  <div class="content">
                    <div class="content-head text-bold md" :style="{ color: message.color }">
                      {{ message.year }}
                      {{ message.era }}
                    </div>
                    <div class="text-bold sm">{{ message.school }}</div>
                    <ul class="card-message sm">
                      <li v-for="(item, index) in formattedMessage(message.message)" :key="index" v-html="item"></li>
                    </ul>
                  </div>
                </v-timeline-item>
              </v-timeline>
            </v-card-text>
            <div class="img">
              <v-avatar size="180px">
                <img src="../../public/images/profile.png" alt="profile">
              </v-avatar>
              <p class="name text-bold md">中西建心</p>
            </div>
          </div>
        </v-card>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      messages: [
        {
          era: '高校',
          school: `駒場東邦高等学校（卒業）`,
          year: '〜2020',
          color: '#7E57C2',
          message: `高2の時に第29回日本数学オリンピックで予選通過`,
        },
        {
          era: '大学',
          school: '慶應義塾大学理工学部情報工学科（卒業）',
          year: '2020〜2024',
          color: '#83ADEA',
          message: `大学2年のpython授業で初めてプログラミングに触れる
          大学3年から今井倫太研究室に所属し、インタラクティブAIの研究を開始`,
        },
        {
          era: '大学院',
          school: '慶応義塾大学大学院理工学研究科開放環境科学専攻（卒業見込）',
          year: '2024〜',
          color: '#009688',
          message: `修士1年生
          同上の研究室に所属`,
        },
      ],
    }
  },
  methods: {
    formattedMessage(message) {
      const links = {
        "第29回日本数学オリンピック": '<a href="https://www.imojp.org/archive/mo2019/jmo2019/yosen_result.html">第29回日本数学オリンピック</a>',
        "今井倫太研究室": '<a href="https://www.ailab.ics.keio.ac.jp/">今井倫太研究室</a>',
      };

      // 各行を改行で分割し、複数の置き換えを行う
      return message.split('\n').map(line => {
        Object.keys(links).forEach(key => {
          line = line.replace(new RegExp(key, 'g'), links[key]);
        });
        return line;
      });
    }
  }
}
</script>

<style scoped>
.about-container {
  width: 100%;
  padding: 16px;
}

.title {
  text-align: left;
  font-size: 24px;
  line-height: 36px;
  font-weight: 700;
}

.card {
  width: 70%;
  text-align: center;
  margin: 0 auto;
}

.card-body {
  display: flex;
  flex-direction: row;
}

.card-text {
  width: 70%;
}

.img {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 16px;
  flex-direction: column;
}

.name {
  padding: 8px 0;
}

.content {
  display: flex;
  text-align: left;
  flex-direction: column;
}

.card-message {
  white-space: pre-line;
}
</style>
