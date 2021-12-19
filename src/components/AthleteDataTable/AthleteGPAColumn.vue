<template>
  <td :class="colorClass">{{Number(schoolGpa).toFixed(2)}}</td>
</template>

<script>
export default {
  name: "AthleteGPAColumn",
  props: {
    schoolGpa: {
      type: Number,
      required: false
    },
    athleteGpa: {
      type: Number,
      required: false
    }
  },
  computed: {
    colorClass() {
      // a switch statement would be more idomatic probably
      if (this.schoolGpa - this.athleteGpa > 0.1) {
        return 'moreThan10';
      } else if (this.schoolGpa - this.athleteGpa > 0) {
        return 'upTo10';
      } else if (this.athleteGpa === this.schoolGpa) {
        return 'isEqual';
      } else if (this.schoolGpa - this.athleteGpa > -0.1) {
        return 'downTo10';
      } else {
        return 'below10';
      }
    }
  }
};
</script>

<style>

.moreThan10 {
  background-color: #d7737d;
}
.upTo10 {
  background-color: #c194b5;
}
.isEqual {
  background-color: #b4a7d6;
}
.downTo10 {
  background-color: #a6a8da;
}
.below10 {
  background-color: #75ace5;
}

</style>