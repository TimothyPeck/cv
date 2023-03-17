<script setup lang="ts">
import { ref } from 'vue';
const dob = new Date('1999-12-07');
let today_date = new Date();
let today_year = today_date.getFullYear();
let today_month = today_date.getMonth();
let today_day = today_date.getDate();
let age = ref(0);
age.value = today_year - dob.getFullYear();

if (today_month < dob.getMonth() - 1) {
  age.value--;
}
if (dob.getMonth() - 1 == today_month && today_day < dob.getDay()) {
  age.value--;
}
defineExpose({ age });
</script>
<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'AboutMeComponent',
  computed: {
    layout() {
      return this.$q.screen.gt.sm ? 'comfortable' : 'dense';
    },
  },
});
</script>
<template>
  <div class="container">
    <h1 class="section-header">{{ $t('about_heading') }}</h1>
    <p class="about-para left-align">{{ $t('about_para1') }}</p>
    <p class="about-para left-align">{{ $t('interests') }}</p>

    <h2 class="mini-header">{{ $t('personal_info') }}</h2>
    <div class="personal-container left-align">
      <p>{{ $t('pob') }}</p>
      <p>{{ $t('born') }}{{ $t('dob') }} - {{ age }} {{ $t('years') }}</p>
      <p>{{ $t('location') }}</p>
    </div>
    <h2 class="mini-header">{{ $t('language_skills') }}</h2>
    <ul class="left-align">
      <li class="en lang-list-item">{{ $t('english_level') }}</li>
      <li class="fr lang-list-item">{{ $t('french_level') }}</li>
      <li class="de lang-list-item">{{ $t('german_level') }}</li>
    </ul>

    <h2 class="mini-header">{{ $t('education') }}</h2>
    <q-timeline :layout="layout" class="centred">
      <q-timeline-entry
        :title="$t('batchelor')"
        subtitle="2019 - 2023"
        color="primary"
        icon="school"
        side="left"
      >
        <div>
          <p>HE-Arc Ingénierie, Neuchâtel, CH</p>
        </div>
      </q-timeline-entry>
      <q-timeline-entry
        :title="$t('cfc')"
        subtitle="2016 - 2019"
        color="primary"
        icon="school"
        side="left"
      >
        <div>
          <p>CPLN, Neuchâtel, CH</p>
        </div>
      </q-timeline-entry>
    </q-timeline>
    <h2 class="mini-header">{{ $t('technos') }}</h2>
    <div class="centred">
      <p>{{ $t('technos_babble') }}</p>
      <div class="split-div">
        <ul>
          <li>Python</li>
          <li>JavaScript</li>
          <li>PHP</li>
          <li>HTML</li>
          <li>CSS</li>
          <li>SQL</li>
        </ul>
        <ul>
          <li>Java</li>
          <li>C++</li>
          <li>C#</li>
          <li>Vue.js</li>
          <li>Quasar</li>
          <li>Qt</li>
        </ul>
        <ul>
          <li>OpenCV</li>
          <li>Git</li>
          <li>Django</li>
          <li>Laravel</li>
          <li>Unity</li>
          <li>Blender</li>
        </ul>
      </div>
    </div>
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

.centred {
  width: 100%;
  justify-content: center;
  align-items: center;
}

.section-header {
  font-size: 3rem;
  font-family: sans-serif;
  width: 100%;
  border-bottom: 3px solid lightblue;
}

.left-align {
  flex-wrap: wrap;
  align-items: flex-start;
  justify-items: flex-start;
  width: 100%;
}

.personal-container {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-start;
}

.about-para {
  font-size: 1rem;
  font-family: sans-serif;
}

.lang-list-item {
  display: flex;
  align-items: center;
  margin: 10px 0;

  line-height: 30px;

  list-style: none;
}

.split-div {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 100%;
}

.lang-list-item::before {
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
  width: 100%;
  border-bottom: 3px solid lightblue;
}

@media screen and (min-width: 1024px) {
  .mini-header,
  .left-align,
  .section-header,
  .centred {
    width: 50%;
  }
}
</style>
