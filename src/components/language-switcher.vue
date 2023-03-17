<template>
  <q-select
    class="lang-select"
    v-model="locale"
    :options="localeOptions"
    :label="$t('language')"
    filled
    dense
    bg-color="teal-3"
    emit-value
    map-options
    options-dense
    square
    style="min-width: 150px"
  />
</template>

<script>
import { useI18n } from 'vue-i18n';

export default {
  setup() {
    const { locale } = useI18n({ useScope: 'global' });

    return {
      locale,
      localeOptions: [
        { value: 'en-UK', label: 'English' },
        { value: 'fr', label: 'French' },
      ],
    };
  },
};
</script>
