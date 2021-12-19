<template>
  <div class="appWrapper">
    <header class="border-t-8 border-cyan text-right">
      <img loading="lazy" encoding="async" alt="SportsRecruits Insights Logo" width="145" height="36" src="../public/sr_insights_logo.png"/>
      <h1 class="text-sm text-charcoal">Academic Fit Report</h1>
    </header>
    <AcademicFitReport/>
  </div>
</template>

<script>
import AcademicFitReport from "@/components/AcademicFitReport.vue";

export default {
  name: "app",
  components: {
    AcademicFitReport
  },
};
</script>

<style>

/* manipulate with JS */
:root {
  --avatarBgColor: red;
}

.appWrapper {
  font-family: 'Roboto', Arial, sans-serif;
}

</style>