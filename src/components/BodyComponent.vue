<template>
  <AboutComponent/>
  <WorkComponent/>
</template>

<script>
import AboutComponent from "@/components/AboutComponent.vue";
import WorkComponent from "@/components/WorkComponent.vue";

export default {
  components: {
    WorkComponent,
    AboutComponent
  },
}
</script>

<style scoped>
</style>
