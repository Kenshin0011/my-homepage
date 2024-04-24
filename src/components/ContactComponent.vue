<template>
  <div class="footer" id="contact">
    <v-footer
        class="bg-indigo-lighten-1 text-center d-flex flex-column"
    >
      <div>
        <v-btn
            v-for="socialMedia in socialMediaLists"
            :href="socialMedia['link']"
            :key="socialMedia"
            :icon="socialMedia['icon']"
            class="mx-4"
            variant="plain"
        ></v-btn>
      </div>
      <div class="title xl">
        Contact
      </div>
      <div class="sm">
        kenshin.nakanishi0011@gmail.com
      </div>
        <v-divider></v-divider>
        <v-card-text class="py-2 white--text text-center">
          {{ new Date().getFullYear() }} — <strong>Kenshin Nakanishi</strong>
        </v-card-text>
    </v-footer>
  </div>
</template>
<script>
export default {
  data() {
    return {
      socialMediaLists: {
        github: {
          icon: 'mdi-github',
          link: 'https://github.com/Kenshin0011',
        },
        mail: {
          icon: 'mdi-email',
          link: 'https://mail.google.com/mail/?view=cm&to=kenshin.nakanishi0011@gmail.com',
        },
        zenn: {
          icon: 'mdi-pen',
          link: 'https://zenn.dev/kenshin0011',
        }
      }
    }
  },
}
</script>

<style scoped>
.footer {
}

.title {
  padding: 8px;
}
</style>
