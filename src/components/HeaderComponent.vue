<template>
  <v-app-bar>
    <v-bottom-navigation
        v-model="value"
        :bg-color="color"
        mode="shift"
    >

      <v-spacer></v-spacer>
      <v-btn @click="$emit('navigate', 'about')">
        <v-icon>mdi-home-circle</v-icon>
        <span>Home</span>
      </v-btn>
      <v-btn @click="$emit('navigate', 'about')">
        <v-icon>mdi-information</v-icon>
        <span>About</span>
      </v-btn>
      <v-btn @click="$emit('navigate', 'works')">
        <v-icon>mdi-laptop</v-icon>
        <span>Work</span>
      </v-btn>
      <v-btn @click="$emit('navigate', 'skill')">
        <v-icon>mdi-pen-plus</v-icon>
        <span>Skills</span>
      </v-btn>
      <v-btn @click="$emit('navigate', 'contact')">
        <v-icon>mdi-card-account-mail</v-icon>
        <span>Contact</span>
      </v-btn>
    </v-bottom-navigation>
  </v-app-bar>
</template>

<script>
export default {
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
        case 3: return 'indigo'
        case 4: return 'blue-grey'
        default: return 'blue-grey'
      }
    },
  },
}
</script>

<style scoped>

</style>
