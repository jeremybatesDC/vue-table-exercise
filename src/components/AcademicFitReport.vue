<template>
<div class="border-t-8 border-cyan" >
  <div class="flex p-2">
    <header class="flex flex-col grow order-last text-right">
      <figure class="flex justify-end">
        <img loading="lazy" encoding="async" alt="SportsRecruits Insights Logo" width="145" height="36" src="../../public/sr_insights_logo.png"/>
      </figure>
      <h1 class="text-sm text-charcoal">Academic Fit Report</h1>
    </header>
    <AthleteProfile :athlete="athlete"/>
  </div>
  <AthleteDataTable :athlete="athlete"/>
</div>
</template>

<script>
import AthleteData from "@/assets/data.json";
import AthleteProfile from "@/components/AthleteDataTable/AthleteProfile.vue";

import AthleteDataTable from "@/components/AthleteDataTable/AthleteDataTable.vue";

export default {
  name: "AcademicFitReport",
  components: {
    AthleteProfile,
    AthleteDataTable
  },
  data() {
    return {
      athlete: AthleteData.data[0],
      lastInitial: null,
    };
  },
};
</script>
