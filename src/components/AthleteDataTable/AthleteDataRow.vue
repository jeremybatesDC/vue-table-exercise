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
      {{school.gpa.min}}
    </td>
    <td class="text-center">
      {{school.gpa.twentyfifth}}
    </td>
    <AthleteGPAColumn class="text-center" :gpa="school.gpa.median"/>
    <td class="text-center">
      {{school.gpa.seventyfifth}}
    </td>
    <td class="text-center">
      {{school.gpa.max}}
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
    }
  }
};
</script>