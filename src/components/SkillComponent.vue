<template>
  <div class="skill-container" id="skills">
    <div class="title text-bold lg">Skills</div>

    <v-card class="card" :class="{ 'mobile-card': isMobileScreen }">
      <v-toolbar color="transparent">
        <v-toolbar-title text="保有資格"/>
      </v-toolbar>
      <div class="card-body">
        <v-card-text class="card-text">
          <ul>
            <li class="md">基本情報技術者試験（2023/4月）</li>
            <li class="md">ITパスポート（2022/3月）</li>
          </ul>
        </v-card-text>
      </div>
    </v-card>
    <v-expansion-panels
        v-model="panel"
        multiple
    >
      <v-expansion-panel>
        <v-expansion-panel-title>よく使う/使っていた</v-expansion-panel-title>
        <v-expansion-panel-text>
          <div class="skills">
            <div v-for="skill in mySkills" :key="skill" class="skill">
              <img :src="skill.img" alt="vue" width="40">
              <p>{{ skill.title }}</p>
            </div>
          </div>
        </v-expansion-panel-text>
      </v-expansion-panel>

      <v-expansion-panel>
        <v-expansion-panel-title>使ったことがある/勉強中</v-expansion-panel-title>
        <v-expansion-panel-text>
          <div class="skills">
            <div v-for="skill in normalSkills" :key="skill" class="skill">
              <img :src="skill.img" alt="vue" width="40">
              <p>{{ skill.title }}</p>
            </div>
          </div>
        </v-expansion-panel-text>
      </v-expansion-panel>

      <v-expansion-panel>
        <v-expansion-panel-title>愛用ツール</v-expansion-panel-title>
        <v-expansion-panel-text>
          <div class="skills">
            <div v-for="skill in likeTools" :key="skill" class="skill">
              <img :src="skill.img" alt="vue" width="40">
              <p>{{ skill.title }}</p>
            </div>
          </div>
        </v-expansion-panel-text>
      </v-expansion-panel>
    </v-expansion-panels>
  </div>
</template>

<script>
export default {
  props: {
    isMobileScreen: { type: Boolean, required: true },
  },
  data() {
    return {
      panel: [0, 1, 2],
      mySkills: [
        {
          img: './images/skills/vue.png',
          title: 'Vue.js',
        },
        {
          img: './images/skills/laravel.png',
          title: 'Laravel',
        },
        {
          img: './images/skills/html.png',
          title: 'html',
        },
        {
          img: './images/skills/css.png',
          title: 'css',
        },
        {
          img: './images/skills/javascript.png',
          title: 'javascript',
        },
        {
          img: './images/skills/c.png',
          title: 'C言語',
        },
        {
          img: './images/skills/python.png',
          title: 'python',
        },
        {
          img: './images/skills/flask.png',
          title: 'flask',
        },
        {
          img: './images/skills/fast-api.png',
          title: 'Fast API',
        },
        {
          img: './images/skills/gpt.png',
          title: 'GPT API',
        },
        {
          img: './images/skills/mysql.png',
          title: 'MySQL',
        },
        {
          img: './images/skills/java.png',
          title: 'Java',
        },
        {
          img: './images/skills/docker.png',
          title: 'Docker',
        },
      ],
      normalSkills: [
        {
          img: './images/skills/react.png',
          title: 'React',
        },
        {
          img: './images/skills/nuxt.png',
          title: 'Nuxt.js',
        },
        {
          img: './images/skills/go.png',
          title: 'Go',
        },
        {
          img: './images/skills/slack-api.png',
          title: 'Slack API',
        },
        {
          img: './images/skills/circleci.png',
          title: 'CircleCI',
        },
        {
          img: './images/skills/unity.png',
          title: 'Unity',
        },
        {
          img: './images/skills/aws.png',
          title: 'AWS',
        },
        {
          img: './images/skills/aws-lambda.png',
          title: 'Lambda',
        },
        {
          img: './images/skills/figma.png',
          title: 'Figma',
        },
        {
          img: './images/skills/jupyter.png',
          title: 'Jupyter',
        },
        {
          img: './images/skills/langchain.png',
          title: 'Lang Chain',
        },
        {
          img: './images/skills/jquery.png',
          title: 'jQuery',
        },
        {
          img: './images/skills/cakephp.png',
          title: 'Cake PHP',
        },
        {
          img: './images/skills/postgre.png',
          title: 'PostgreSQL',
        },
        {
          img: './images/skills/dynamodb.png',
          title: 'Dynamo DB',
        },
        {
          img: './images/skills/chroma.png',
          title: 'Chroma',
        },
        {
          img: './images/skills/ngrok.png',
          title: 'ngrok',
        },
        {
          img: './images/skills/nginx.png',
          title: 'nginx',
        },
        {
          img: './images/skills/apache.png',
          title: 'Apache',
        },
      ],
      likeTools: [
        {
          img: './images/skills/github.png',
          title: 'Github',
        },
        {
          img: './images/skills/raycast.png',
          title: 'Raycast',
        },
        {
          img: './images/skills/phpstorm.png',
          title: 'PhpStorm',
        },
        {
          img: './images/skills/notion.png',
          title: 'Notion',
        },
      ]
    }
  }
}
</script>

<style scoped>
.skill-container {
  padding: 90px 32px;
}

.title {
  padding-bottom: 16px;
}

.skills {
  display: flex;
  flex-wrap: wrap;
}

.skill {
  display: flex;
  padding: 8px 16px;
  align-items: center;
  justify-content: flex-end;
  flex-direction: column;
  flex: 0 1 120px;
}

.card {
  width: 50%;
  margin: 16px auto;
}

.mobile-card {
  width: 90%;
}

.card-body {
  padding: 0 16px;
}
</style>
