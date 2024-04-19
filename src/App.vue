<template>
  <v-app>
    <HeaderComponent @navigate="scrollTo"/>
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
