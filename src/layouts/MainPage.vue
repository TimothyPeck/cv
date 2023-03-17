<script>
import { ref } from 'vue';
import aboutMeVue from '../components/about-me.vue';
import languageSwitcherVue from '../components/language-switcher.vue';

export default {
  setup() {
    const rightDrawerOpen = ref(false);
    return {
      rightDrawerOpen,
      toggleRightDrawer() {
        rightDrawerOpen.value = !rightDrawerOpen.value;
      },
    };
  },
  components: { aboutMeVue, languageSwitcherVue },
};
</script>
<template>
  <q-layout view="hHh lpR fFf">
    <q-header reveal elevated class="bg-primary text-white">
      <q-toolbar>
        <q-toolbar-title> Timothy Roy Peck </q-toolbar-title>

        <q-space />
        <languageSwitcherVue />
        <q-btn dense flat round icon="menu" @click="toggleRightDrawer" />
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="rightDrawerOpen"
      show-if-above
      :width="200"
      :breakpoint="400"
      side="right"
      bordered
    >
      <q-scroll-area
        style="
          height: calc(100% - 150px);
          margin-top: 150px;
          border-right: 1px solid #ddd;
        "
      >
        <q-list padding>
          <a href="mailto:t.r.peck@hotmail.com" class="sidebar-link">
            <q-item clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="send"></q-icon>
              </q-item-section>

              <q-item-section> Email </q-item-section>
            </q-item>
          </a>

          <a href="https://github.com/TimothyPeck/" class="sidebar-link">
            <q-item clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="fa-brands fa-github"></q-icon>
              </q-item-section>

              <q-item-section> GitHub </q-item-section>
            </q-item>
          </a>

          <a
            href="https://www.linkedin.com/in/timothy-peck/"
            class="sidebar-link"
          >
            <q-item clickable v-ripple>
              <q-item-section avatar>
                <q-icon name="fa-brands fa-linkedin"></q-icon>
              </q-item-section>

              <q-item-section> Linkedin </q-item-section>
            </q-item>
          </a>
        </q-list>
      </q-scroll-area>

      <q-img
        class="absolute-top"
        src="https://images.unsplash.com/photo-1678905029643-741e60ef88d5"
        style="height: 150px"
      >
        <div class="absolute-bottom bg-transparent">
          <q-avatar size="56px" class="q-mb-sm">
            <img src="../assets/forum_beaulieu_ag-094.jpg" />
          </q-avatar>
        </div>
      </q-img>
    </q-drawer>

    <q-page-container>
      <aboutMeVue />
    </q-page-container>
  </q-layout>
</template>
<style>
.sidebar-link {
  text-decoration: none;
  color: inherit;
}

img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.LI-simple-link {
  text-decoration: none;
  color: inherit;
  transition: all 0.2s ease-in-out;
}

.fa-linkedin {
  margin-right: 0.5rem;
  color: #0077b5;
}

.semi-opaque {
  background-color: rgba(0, 0, 0, 0.8);
  border-radius: 0.1rem;
  padding: 0.1rem 0.5rem;
}

@media screen and (min-width: 1024px) {
  .LI-simple-link:hover,
  .LI-simple-link:active {
    text-decoration: underline;
  }
}
</style>
