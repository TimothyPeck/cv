<script setup lang="ts"></script>
<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'FooterComponent',
});
</script>
<template>
  <q-footer>
    <q-toolbar>
      <q-toolbar-title>
        <q-btn
          flat
          label="Github"
          icon="fab fa-github"
          href="https://github.com/TimothyPeck/"
          target="_blank"
        />
        <q-btn
          flat
          label="LinkedIn"
          icon="fab fa-linkedin"
          href="https://www.linkedin.com/in/timothy-peck/"
          target="_blank"
        />
        <q-btn
          flat
          label="Email"
          icon="fas fa-envelope"
          href="mailto:t.r.peck@hotmail.com"
          target="_blank"
        />
      </q-toolbar-title>
      <p>{{ $t('thanks') }}</p>
    </q-toolbar>
  </q-footer>
</template>
