<template>
  <div class="header-container" id="home">
    <v-app-bar>
      <v-bottom-navigation
          v-model="value"
          :bg-color="color"
          mode="shift"
      >
        <div v-if="!isMobileScreen" class="container">
          <div class="title lg text-bold">Kenshin's Portfolio</div>
          <div class="button-container">
            <v-btn @click="$emit('navigate', 'home')">
              <v-icon>mdi-home-circle</v-icon>
              <span>Home</span>
            </v-btn>
            <v-btn @click="$emit('navigate', 'about')">
              <v-icon>mdi-information</v-icon>
              <span>About</span>
            </v-btn>
            <v-btn @click="$emit('navigate', 'affiliation')">
              <v-icon>mdi-paw</v-icon>
              <span>affiliation</span>
            </v-btn>
            <v-btn @click="$emit('navigate', 'works')">
              <v-icon>mdi-laptop</v-icon>
              <span>Works</span>
            </v-btn>
            <v-btn @click="$emit('navigate', 'skills')">
              <v-icon>mdi-pen-plus</v-icon>
              <span>Skills</span>
            </v-btn>
            <v-btn @click="$emit('navigate', 'contact')">
              <v-icon>mdi-card-account-mail</v-icon>
              <span>Contact</span>
            </v-btn>
          </div>
        </div>
        <div v-else class="mobile-container">
          <div class="button-container">
            <v-btn density="compact" size="x-small" @click="$emit('navigate', 'home')">
              <v-icon>mdi-home-circle</v-icon>
            </v-btn>
            <v-btn density="compact" size="x-small" @click="$emit('navigate', 'about')">
              <v-icon>mdi-information</v-icon>
            </v-btn>
            <v-btn density="compact" size="x-small" @click="$emit('navigate', 'affiliation')">
              <v-icon>mdi-paw</v-icon>
            </v-btn>
            <v-btn density="compact" size="x-small" @click="$emit('navigate', 'works')">
              <v-icon>mdi-laptop</v-icon>
            </v-btn>
            <v-btn density="compact" size="x-small" @click="$emit('navigate', 'skills')">
              <v-icon>mdi-pen-plus</v-icon>
            </v-btn>
            <v-btn density="compact" size="x-small" @click="$emit('navigate', 'contact')">
              <v-icon>mdi-card-account-mail</v-icon>
            </v-btn>
          </div>
        </div>
      </v-bottom-navigation>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  props: {
    isMobileScreen: { type: Boolean, required: true },
  },
  data() {
    return {
      value: 0
    }
  },
  computed: {
    color () {
      switch (this.value) {
        case 0: return '#1E1F22'
        case 1: return 'teal'
        case 2: return 'brown'
        case 3: return '#83ADEA'
        case 4: return 'indigo'
        case 5: return 'blue-grey'
        default: return 'blue-grey'
      }
    },
  },
}
</script>

<style scoped>
.header-container {
  height: 56px;
}

.title {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 250px;
  padding: 16px;
}

.mobile-title {
  width: 80px;
  padding: 12px;
}

.v-application .v-app-bar {
  padding-top: 0;
  margin-top: -8px;
}

.button-container {
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  display: flex;
  width: 100%;
  justify-content: space-between;
}

.mobile-container {
  display: flex;
  width: 100%;
  justify-content: flex-end;
}
</style>
