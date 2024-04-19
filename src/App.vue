<template>
  <v-app>
    <HeaderComponent @navigate="scrollTo"/>
    <HomeComponent/>
  </v-app>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import ContactComponent from "@/components/ContactComponent.vue";
import HomeComponent from "@/components/HomeComponent.vue";
import BodyComponent from "@/components/BodyComponent.vue";

export default {
  components: {
    BodyComponent,
    HomeComponent,
    ContactComponent,
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
