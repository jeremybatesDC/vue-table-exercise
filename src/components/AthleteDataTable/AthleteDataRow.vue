<template>
  <tr>
    <th scope="row" class="text-left py-2 px-1">
      {{school.school}}
    </th>
    <td class="text-center">
      {{school.division}}
    </td>
    <td class="text-left">
      {{school.conference}}
    </td>
    <td class="text-center">
      {{school.ranking}}
    </td>
    <td class="text-center">
      {{Number(school.gpa.min).toFixed(2)}}
    </td>
    <td class="text-center">
      {{Number(school.gpa.twentyfifth).toFixed(2)}}
    </td>
    <AthleteGPAColumn class="text-center" :schoolGpa="school.gpa.median" :athleteGpa="athleteGpa"/>
    <td class="text-center">
      {{Number(school.gpa.seventyfifth).toFixed(2)}}
    </td>
    <td class="text-center">
      {{Number(school.gpa.max).toFixed(2)}}
    </td>
    <td class="text-center">
      {{school.sat.reading.min}}-{{school.sat.reading.max}}
    </td>
    <td class="text-center">
      {{school.sat.math.min}}-{{school.sat.math.max}}
    </td>
    <td class="text-center">
      {{school.act.min}}-{{school.act.max}}
    </td>
  </tr>
</template>

<script>
import AthleteGPAColumn from "@/components/AthleteDataTable/AthleteGPAColumn.vue";

export default {
  name: "AthleteDataRow",
  components: {
    AthleteGPAColumn
  },
  props: {
    school: {
      type: Object,
      required: false
    },
    athleteGpa: {
      type: Number,
      required: false
    }
  }
};
</script>