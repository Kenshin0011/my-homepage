<template>
  <v-app-bar>
    <v-spacer></v-spacer>
    <v-btn text @click="$emit('navigate', 'about')">About</v-btn>
    <v-btn text @click="$emit('navigate', 'works')">Works</v-btn>
    <v-btn text @click="$emit('navigate', 'skill')">Skill</v-btn>
    <v-btn text @click="$emit('navigate', 'contact')">Contact</v-btn>
  </v-app-bar>
</template>

<script>
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
