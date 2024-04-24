<template>
  <AboutComponent/>
  <AffiliationComponent/>
  <WorksComponent />
  <SkillComponent/>
</template>

<script>
import AboutComponent from "@/components/AboutComponent.vue";
import AffiliationComponent from "@/components/AffiliationComponent.vue";
import SkillComponent from "@/components/SkillComponent.vue";
import WorksComponent from "@/components/WorksComponent.vue";

export default {
  components: {
    WorksComponent,
    SkillComponent,
    AffiliationComponent,
    AboutComponent
  },
}
</script>

<style scoped>
</style>
