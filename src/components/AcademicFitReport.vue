<template>
  <div>
    <div class="text-sm">
      <!-- v-if image -->
      <!-- v-else avatar -->
      <img v-if="athlete.profile_image" loading="lazy" encoding="async" class="rounded-full" :alt="athlete.name" width="64" height="64" :src="athlete.profile_image"/>
      <span ref="avatar" class="avatar flex w-16 h-16 rounded-full text-center justify-center items-center">{{initials()}}</span>

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
      athlete: AthleteData.data[0],
      lastInitial: null,
    };
  },
  computed: {
    
  },
  methods: {
    initials(){
      let stringArray = this.athlete.name.split(' ');
      this.lastInitial = stringArray[1].charAt(0).toUpperCase();

      if(this.lastInitial === 'A' || this.lastInitial === 'B' || this.lastInitial === 'C' || this.lastInitial === 'D' || this.lastInitial === 'E'){
        console.log('A - E')
      }
      else if(this.lastInitial === 'F' || this.lastInitial === 'G' || this.lastInitial === 'H' || this.lastInitial === 'I' || this.lastInitial === 'J'){
        console.log('F - J')
      }

      else if(this.lastInitial === 'K' || this.lastInitial === 'L' || this.lastInitial === 'M' || this.lastInitial === 'N' || this.lastInitial === 'O'){
        console.log('K - O')
      }
      else if(this.lastInitial === 'P' || this.lastInitial === 'Q' || this.lastInitial === 'R' || this.lastInitial === 'S' || this.lastInitial === 'T'){
        console.log('P - T')
      }
      else {
        console.log('U - Z')
      }

      return `${this.athlete.name.charAt(0)}${this.lastInitial}`;
    }
  }
};
</script>

<style>

.avatar {
  background-color: var(--avatarBgColor);
}
</style>