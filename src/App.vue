<template>
  <v-app>
    <div class="main">
      <HeaderComponent
          @navigate="scrollTo"
          :is-mobile-screen="isMobileScreen"
      />
      <HomeComponent />
      <BodyComponent />
      <ContactComponent />
    </div>
  </v-app>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import HomeComponent from "./components/HomeComponent.vue";
import BodyComponent from "./components/BodyComponent.vue";
import ContactComponent from "@/components/ContactComponent.vue";

export default {
  components: {
    ContactComponent,
    BodyComponent,
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
.main {
  background-color: var(--vt-c-text-dark-2);
}
</style>
