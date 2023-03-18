<script setup lang="ts"></script>
<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'FooterComponent',
});
</script>
<template>
  <q-footer>
    <q-toolbar class="footer">
      <q-toolbar-title>
        <q-btn
          flat
          icon="fab fa-github"
          href="https://github.com/TimothyPeck/"
          target="_blank"
        />
        <q-btn
          flat
          icon="fab fa-linkedin"
          href="https://www.linkedin.com/in/timothy-peck/"
          target="_blank"
        />
        <q-btn flat icon="fas fa-envelope" href="mailto:t.r.peck@hotmail.com" />
      </q-toolbar-title>
      <q-space></q-space>
      <div>
        {{ $t('thanks')
        }}<a
          href="https://jeanne-michel.vercel.app"
          target="_blank"
          class="thanks-link"
          >Jeanne</a
        >{{ $t('thanks_cont') }}
      </div>
    </q-toolbar>
  </q-footer>
</template>
<style>
.footer {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
}

.thanks-link {
  color: #fff;
}

@media screen and (min-width: 1024px) {
  .footer {
    flex-direction: row;
    align-items: flex-start;
  }
}
</style>
