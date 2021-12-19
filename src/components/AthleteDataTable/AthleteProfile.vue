<template>
<div class="text-sm flex">
    <figure class="flex items-center shrink-0">
        <img v-if="athlete.profile_image" loading="lazy" encoding="async" class="rounded-full" :alt="athlete.name" width="64" height="64" :src="athlete.profile_image"/>
        <span v-else ref="avatar" class="avatar flex w-16 h-16 rounded-full text-lg font-bold text-center justify-center items-center">{{initials()}}</span>
    </figure>
    <div class="pl-4">
        <h2 class="text-base text-cyan font-bold">{{athlete.name}}</h2>
        <ul class="profile__ul md:columns-2">
            <li>
                <strong>Sport: </strong>
                <span class="text-charcoal">{{athlete.sport}}</span>
            </li>
            <li>
                <strong>Class: </strong>
                <span class="text-charcoal">{{athlete.grad_year}}</span>
            </li>
            <li>
                <strong>Club: </strong>
                <span class="text-charcoal">{{athlete.club.name}}</span>
            </li>
            <li>
                <strong>High School: </strong>
                <span class="text-charcoal">{{athlete.high_school.name}}</span>
            </li>
            <li>
                <strong>GPA: </strong>
                <span class="text-charcoal">{{athlete.gpa}}</span>
            </li>
            <li>
                <strong>Desired Major: </strong>
                <span class="text-charcoal">{{athlete.major}}</span>
            </li>
        </ul>
    </div>
</div>
</template>

<script>

export default {
  name: "AthleteProfile",
  props: {
    athlete: {
      type: Object,
      required: false
    }
  },
  methods: {
    initials(){
      let stringArray = this.athlete.name.split(' ');
      this.lastInitial = stringArray[1].charAt(0).toUpperCase();
      let colorToSet;
      if(this.lastInitial === 'A' || this.lastInitial === 'B' || this.lastInitial === 'C' || this.lastInitial === 'D' || this.lastInitial === 'E'){
        colorToSet = '#f1603c';
      }
      else if(this.lastInitial === 'F' || this.lastInitial === 'G' || this.lastInitial === 'H' || this.lastInitial === 'I' || this.lastInitial === 'J'){
        colorToSet ='#6082fa';
      }
      else if(this.lastInitial === 'K' || this.lastInitial === 'L' || this.lastInitial === 'M' || this.lastInitial === 'N' || this.lastInitial === 'O'){
        colorToSet = '#827cb8';
      }
      else if(this.lastInitial === 'P' || this.lastInitial === 'Q' || this.lastInitial === 'R' || this.lastInitial === 'S' || this.lastInitial === 'T'){
        colorToSet = '#0097a4';
      }
      else if(this.lastInitial === 'U' || this.lastInitial === 'V' || this.lastInitial === 'W' || this.lastInitial === 'X' || this.lastInitial === 'Y'){
        colorToSet = '#ffe066';
      }
      else {
        colorToSet = '#ffa94d';
      }

      document.body.style.setProperty('--avatarBgColor', colorToSet);

      return `${this.athlete.name.charAt(0)}${this.lastInitial}`;
    }
  }
};
</script>

<style>

.avatar {
  background-color: var(--avatarBgColor);
  aspect-ratio: 1/1;
}

</style>