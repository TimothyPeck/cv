<script setup lang="ts"></script>
<template>
  <div class="container">
    <h1 class="section-header">{{ $t('projects') }}</h1>
    <div class="container split-div centred">
      <q-card>
        <q-card-section>
          <h3>Rattus</h3>
        </q-card-section>
        <q-card-section>
          <div>
            <p>{{ $t('rattus_description') }}</p>
            <p>Technologies: Unity 3D, C#</p>
          </div>
        </q-card-section>
      </q-card>
      <q-card>
        <q-card-section>
          <h3>Torterraria</h3>
        </q-card-section>
        <q-card-section>
          <div>
            <p>{{ $t('tort_description') }}</p>
            <p>Technologies: Unity, C#</p>
          </div>
        </q-card-section>
      </q-card>
      <q-card>
        <q-card-section>
          <h3>The-ASSistant</h3>
        </q-card-section>
        <q-card-section>
          <div>
            <p>{{ $t('assistant_description') }}</p>
            <p>Technologies: Laravel, PHP, HTML, CSS, JS</p>
          </div>
        </q-card-section>
      </q-card>
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

.split-div {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 100%;
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
