<script setup>
import { ref, defineExpose } from 'vue';
const dob = new Date('1999-12-07');
let today_date = new Date();
let today_year = today_date.getFullYear();
let today_month = today_date.getMonth();
let today_day = today_date.getDate();
let age = ref(null);
age.value = today_year - dob.getFullYear();

if (today_month < dob.getMonth() - 1) {
  age.value--;
}
if (dob.getMonth() - 1 == today_month && today_day < dob.getDay()) {
  age.value--;
}
defineExpose({ age });
</script>
<!-- <script>
// export default {
//   name: 'AboutMe',
//   methods: {
//     getAge() {

//       return age;
//     },
//   },
//   setup() {
//     const age = ref(getAge());
//     return { age };
//   },
// };
</script>-->
<template>
  <div class="container">
    <h1 class="section-header">{{ $t('about_heading') }}</h1>
    <p class="about-para left-align">{{ $t('about_para1') }}</p>

    <h2 class="mini-header">{{ $t('personal_info') }}</h2>
    <ul class="left-align">
      <li>{{ $t('pob') }}</li>
      <li>{{ $t('dob') }} - {{ age }} {{ $t('years') }}</li>
      <li>{{ $t('location') }}</li>
    </ul>
    <h2 class="mini-header">{{ $t('language_skills') }}</h2>
    <ul class="left-align">
      <li class="en">{{ $t('english_level') }}</li>
      <li class="fr">{{ $t('french_level') }}</li>
      <li class="de">{{ $t('german_level') }}</li>
    </ul>
  </div>
</template>
<style>
.container {
  display: flex;
  width: 100%;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.section-header {
  font-size: 3rem;
  font-family: sans-serif;
  width: 50%;
  border-bottom: 3px solid lightblue;
}

.left-align {
  flex-wrap: wrap;
  align-items: flex-start;
  justify-items: flex-start;
  width: 50%;
}

.about-para {
  font-size: 1rem;
  font-family: sans-serif;
}

li {
  display: flex;
  align-items: center;
  margin: 10px 0;

  line-height: 30px;

  list-style: none;
}

li::before {
  display: block;
  flex-shrink: 0;
  width: 33px;
  height: 33px;
  margin-right: 10px;
  background-size: contain;
  content: '';
}

.en::before {
  content: '🇬🇧';
}

.fr::before {
  content: '🇫🇷';
}

.de::before {
  content: '🇩🇪';
}

.mini-header {
  font-size: 1.5rem;
  font-family: sans-serif;
  width: 50%;
  border-bottom: 3px solid lightblue;
}
</style>
