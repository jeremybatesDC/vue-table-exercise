<template>
  <td>{{gpa}}</td>
</template>

<script>
export default {
  name: "AthleteGPAColumn",
  props: {
    gpa: {
      type: Number,
      required: false
    }
  }
};
</script>

<style>

/* maybe use data attributes*/

.moreThan10 {

}
.upTo10 {
  
}

.isEqual {
  
}

.downTo10 {
  
}

.below10 {
  
}

</style>