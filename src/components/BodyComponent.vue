<template>
  <AboutComponent/>
  <AffiliationComponent/>
  <SkillComponent/>
</template>

<script>
import AboutComponent from "@/components/AboutComponent.vue";
import AffiliationComponent from "@/components/AffiliationComponent.vue";
import SkillComponent from "@/components/SkillComponent.vue";

export default {
  components: {
    SkillComponent,
    AffiliationComponent,
    AboutComponent
  },
}
</script>

<style scoped>
</style>
