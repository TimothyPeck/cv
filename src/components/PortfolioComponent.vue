<script setup lang="ts"></script>
<template>
  <div class="container">
    <h1 class="section-header">{{ $t('projects') }}</h1>
    <div class="split-div centred tech-container">
      <q-card>
        <q-card-section>
          <a
            href="https://github.com/TimothyPeck/Rattus"
            target="_blank"
            class="portfolio-link"
          >
            <h3>Rattus</h3>
          </a>
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
          <a
            href="https://github.com/TimothyPeck/Torterraria"
            target="_blank"
            class="portfolio-link"
          >
            <h3>Torterraria</h3>
          </a>
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
          <a
            href="https://github.com/HE-Arc/The-ASSistant"
            target="_blank"
            class="portfolio-link"
          >
            <h3>The-ASSistant</h3>
          </a>
        </q-card-section>
        <q-card-section>
          <div>
            <p>{{ $t('assistant_description') }}</p>
            <p>Technologies: Laravel, PHP, HTML, CSS, JS</p>
          </div>
        </q-card-section>
      </q-card>
      <q-card>
        <q-card-section>
          <a
            href="https://github.com/HE-Arc/FirstPass"
            target="_blank"
            class="portfolio-link"
          >
            <h3>FirstPass</h3>
          </a>
        </q-card-section>
        <q-card-section>
          <div>
            <p>{{ $t('assistant_description') }}</p>
            <p>Technologies: Django, Vue, JavaScript, CSS</p>
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

.tech-container {
  flex-direction: column;
  min-width: 100%;
}

.q-card {
  width: 100%;
  margin: 1rem;
  min-height: 280px;
}

.portfolio-link {
  color: black;
}

h3 {
  font-size: 2.1rem;
  margin: 0;
}

@media screen and (min-width: 1024px) {
  .mini-header,
  .left-align,
  .section-header,
  .centred,
  .tech-container {
    width: 50%;
  }

  .q-card {
    width: 30%;
  }

  .tech-container {
    flex-direction: row;
    min-width: 50%;
  }

  .portfolio-link {
    transition: all 0.3s ease-in-out;
  }

  .portfolio-link:hover {
    color: #003049;
  }
}
</style>
