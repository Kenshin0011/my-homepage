<template>
  <AboutComponent :is-mobile-screen="isMobileScreen"/>
  <AffiliationComponent/>
  <WorksComponent :is-mobile-screen="isMobileScreen"/>
  <SkillComponent :is-mobile-screen="isMobileScreen"/>
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
  props: {
    isMobileScreen: { type: Boolean, required: true },
  },
}
</script>

<style scoped>
</style>
