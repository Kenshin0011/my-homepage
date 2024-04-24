<template>
  <AboutComponent/>
  <WorkComponent/>
  <SkillComponent/>
</template>

<script>
import AboutComponent from "@/components/AboutComponent.vue";
import WorkComponent from "@/components/WorkComponent.vue";
import SkillComponent from "@/components/SkillComponent.vue";

export default {
  components: {
    SkillComponent,
    WorkComponent,
    AboutComponent
  },
}
</script>

<style scoped>
</style>
