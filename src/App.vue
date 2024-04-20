<template>
  <v-app>
    <HeaderComponent
        @navigate="scrollTo"
        :is-mobile-screen="isMobileScreen"
    />
    <HomeComponent/>
  </v-app>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import HomeComponent from "@/components/HomeComponent.vue";

export default {
  components: {
    HomeComponent,
    HeaderComponent,
  },
  computed: {
    isMobileScreen() {
      return this.$vuetify.display.smAndDown;
    },
  },
  methods: {
    scrollTo(section) {
      const element = document.getElementById(section);
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' });
      }
    }
  }
}
</script>

<style scoped>
</style>
