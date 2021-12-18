<template>
  <div>
    <table>
      <thead>
        <tr>
          <!-- should be based off keys -->
          <th>School Name</th>
          <th>Athletic Div</th>
          <th>Conference</th>
          <th>Ranking*(DI NCAA) (DII & DIII Hero Sports)</th>

          <th>Min</th>
          <th>25%</th>
          <th>50%</th>
          <th>75%</th>
          <th>Max</th>

          <th>SAT Reading*** 25%-75%</th>
          <th>SAT Math*** 25%-75%</th>
          <th>ACT Composite*** 25%-75%</th>
        </tr>
      </thead>
      <tbody>
        <!-- for each record, add a row component -->
        <AthleteDataRow v-for="(school, index) in athlete.report" :key="index" :school="school"/>
      </tbody> 
      <tfoot>
        <tr>
          <td>
            <p>*Rankings</p>
            <p>**GPA</p>
            <p>***SAT</p>
          </td>
        </tr>
      </tfoot>
    </table>
  </div>
</template>

<script>
import AthleteDataRow from "@/components/AthleteDataTable/AthleteDataRow.vue";

export default {
  name: "AthleteDataTable",
  components: {
    AthleteDataRow
  },
  props: {
    athlete: {
      type: Object,
      required: false
    }
  }
};
</script>