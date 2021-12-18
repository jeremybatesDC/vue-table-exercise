<template>
  <div>
    <div class="text-sm">
      <h2 class="text-base text-cyan font-bold">{{athlete.name}}</h2>
      <ul>
        <li>
          <strong>Sport:</strong>
          <span class="text-charcoal">{{athlete.sport}}</span>
        </li>
        <li>
          <strong>Class:</strong>
          <span class="text-charcoal">{{athlete.grad_year}}</span>
        </li>
        <li>
          <strong>Club:</strong>
          <span class="text-charcoal">{{athlete.club.name}}</span>
        </li>
        <li>
          <strong>High School:</strong>
          <span class="text-charcoal">{{athlete.high_school.name}}</span>
        </li>
        <li>
          <strong>GPA:</strong>
          <span class="text-charcoal">{{athlete.gpa}}</span>
        </li>
        <li>
          <strong>Desired Major:</strong>
          <span class="text-charcoal">{{athlete.major}}</span>
        </li>
      </ul>
    </div>
    <AthleteDataTable :athlete="athlete"/>
  </div>
</template>

<script>
import AthleteData from "@/assets/data.json";
import AthleteDataTable from "@/components/AthleteDataTable/AthleteDataTable.vue";

export default {
  name: "AcademicFitReport",
  components: {
    AthleteDataTable
  },
  data() {
    return {
      athlete: AthleteData.data[0]
    };
  }
};
</script>