<template>
  <div class="skill-container" id="skills">
    <div class="title text-bold lg">Skills</div>
    <v-expansion-panels
        v-model="panel"
        multiple
    >
      <v-expansion-panel>
        <v-expansion-panel-title>よく使う</v-expansion-panel-title>
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
        <v-expansion-panel-title>使ったことがある</v-expansion-panel-title>
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
        <v-expansion-panel-title>勉強中</v-expansion-panel-title>
        <v-expansion-panel-text>
          <div class="skills">
            <div v-for="skill in learningSkills" :key="skill" class="skill">
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
  data() {
    return {
      panel: [0, 1, 2],
      mySkills: [
        {
          img: './public/images/skills/vue.png',
          title: 'Vue.js',
        },
        {
          img: './public/images/skills/laravel.png',
          title: 'Laravel',
        },
        {
          img: './public/images/skills/html.png',
          title: 'html',
        },
        {
          img: './public/images/skills/css.png',
          title: 'css',
        },
        {
          img: './public/images/skills/javascript.png',
          title: 'javascript',
        },
        {
          img: './public/images/skills/c.png',
          title: 'C言語',
        },
        {
          img: './public/images/skills/python.png',
          title: 'python',
        },
        {
          img: './public/images/skills/flask.png',
          title: 'flask',
        },
        {
          img: './public/images/skills/gpt.png',
          title: 'GPT API',
        },
        {
          img: './public/images/skills/mysql.png',
          title: 'mysql',
        },
        {
          img: './public/images/skills/java.png',
          title: 'Java',
        },
      ],
      normalSkills: [
        {
          img: './public/images/skills/slack-api.png',
          title: 'Slack API',
        },
        {
          img: './public/images/skills/docker.png',
          title: 'Docker',
        },
        {
          img: './public/images/skills/unity.png',
          title: 'Unity',
        },
        {
          img: './public/images/skills/aws.png',
          title: 'AWS',
        },
        {
          img: './public/images/skills/aws-lambda.png',
          title: 'Lambda',
        },
        {
          img: './public/images/skills/figma.png',
          title: 'Figma',
        },
        {
          img: './public/images/skills/fast-api.png',
          title: 'Fast API',
        },
        {
          img: './public/images/skills/jupyter.png',
          title: 'Jupyter',
        },
        {
          img: './public/images/skills/langchain.png',
          title: 'Lang Chain',
        },
        {
          img: './public/images/skills/jquery.png',
          title: 'jQuery',
        },
        {
          img: './public/images/skills/cakephp.png',
          title: 'Cake PHP',
        },
        {
          img: './public/images/skills/dynamodb.png',
          title: 'Dynamo DB',
        },
        {
          img: './public/images/skills/chroma.png',
          title: 'Chroma',
        },
        {
          img: './public/images/skills/ngrok.png',
          title: 'ngrok',
        },
        {
          img: './public/images/skills/nginx.png',
          title: 'nginx',
        },
        {
          img: './public/images/skills/apache.png',
          title: 'Apache',
        },
      ],
      learningSkills: [
        {
          img: './public/images/skills/react.png',
          title: 'React',
        },
        {
          img: './public/images/skills/go.png',
          title: 'Go',
        },
        {
          img: './public/images/skills/aws.png',
          title: 'AWS',
        },
      ]
    }
  }
}
</script>

<style scoped>
.skill-container {
  padding: 32px;
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
</style>
