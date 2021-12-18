<template>
  <tr>
    <th scope="row">
      {{school.school}}
    </th>
    <td>
      {{school.division}}
    </td>
    <td>
      {{school.conference}}
    </td>
    <td>
      {{school.ranking}}
    </td>
    <td>
      {{school.gpa.min}}
    </td>
    <td>
      {{school.gpa.twentyfifth}}
    </td>
    <AthleteGPAColumn :gpa="school.gpa.median"/>
    <td>
      {{school.gpa.seventyfifth}}
    </td>
    <td>
      {{school.gpa.max}}
    </td>
    <td>
      {{school.sat.reading.min}}-{{school.sat.reading.max}}
    </td>
    <td>
      {{school.sat.math.min}}-{{school.sat.math.max}}
    </td>

    <td>
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