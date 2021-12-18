<template>
  <div>
    <div class="info">
      <h2>{{athlete.name}}</h2>
      <ul>
        <li>
          <label>Sport:</label>
          {{athlete.sport}}
        </li>
        <li>
          <label>Class:</label>
          {{athlete.grad_year}}
        </li>
        <li>
          <label>Club:</label>
          {{athlete.club.name}}
        </li>
        <li>
          <label>High School:</label>
          {{athlete.high_school.name}}
        </li>
        <li>
          <label>GPA:</label>
          {{athlete.gpa}}
        </li>
        <li>
          <label>Desired Major:</label>
          {{athlete.major}}
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