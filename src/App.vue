<template>
  <router-view />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useQuasar } from 'quasar';

export default defineComponent({
  name: 'App',

  setup() {
    const $q = useQuasar();
    $q.lang.getLocale(); // returns a string
  },
});
</script>
