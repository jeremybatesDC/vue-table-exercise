<template>
  <div class="appWrapper max-w-5xl my-0 mx-auto">
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