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