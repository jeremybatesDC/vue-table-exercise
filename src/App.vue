<template>
  <div class="appWrapper">
    <header>
      Logo
      <h1>Academic Fit Report</h1>
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

.appWrapper {
  font-family: 'Roboto', Arial, sans-serif;
}

</style>