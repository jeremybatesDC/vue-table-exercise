<template>
  <div class="border-b-8 border-cyan overflow-x-auto">
    <table class="text-xxs tabular-nums">
      <thead class="bg-black text-white">
        <tr>
          <!-- should be based off keys -->
          <th class="bg-black px-1">School Name</th>
          <th>Athletic Div</th>
          <th>Conference</th>
          <th>Ranking*
            <div>(DI NCAA)</div>
            <div>(DII & DIII Hero Sports)</div>
          </th>

          <th>Min</th>
          <th>25%</th>
          <th>50%</th>
          <th>75%</th>
          <th>Max</th>

          <th>SAT Reading***
            <div>25%-75%</div>
          </th>
          <th>SAT Math***
            <div>25%-75%</div>
          </th>
          <th>ACT Composite***
            <div>25%-75%</div>
          </th>
        </tr>
      </thead>
      <tbody class="text-charcoal">
        <!-- for each record, add a row component -->
        <AthleteDataRow v-for="(school, index) in athlete.report" :key="index" :school="school"/>
      </tbody> 
      <tfoot>
        <tr>
          <td colspan="12">
            <p>*Rankings for Division I schools based on NCAA data (www.ncaa.com) and rankings for Division II & III schools are based on data from Hero Sports (www.herosports.com/rankings)</p>
            <p>**GPA is based on SportsRecruits members who have shown interest in (favorited) the school and have provided their GPA on their profile</p>
            <p>***SAT and ACT scores based on national data provided by the National Center of Education Statistics- https://nces.ed.gov/ipeds/</p>
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

<style>

tbody tr:nth-child(even),
tbody tr:nth-child(even) th:first-child{
  background-color: #e8f0fe;
}

tbody tr:nth-child(odd) th:first-child{
  background-color: #fff;
}

thead th:first-child,
tbody th{
  position: sticky;
  left: 0;
}

</style>