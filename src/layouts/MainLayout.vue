

<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="header">
      <q-toolbar :class="$q.dark.isActive ? 'text-primary' : 'text-dark'">
        <q-toolbar-title>Get Frog</q-toolbar-title>

        <q-btn
          @click="toggleDarkMode"
          flat
          round
          dense
          :icon="$q.dark.isActive ? 'eva-sun-outline' : 'eva-moon-outline'"
          class="q-mr-md"
        >
          <q-tooltip>Toggle Dark Mode</q-tooltip>
        </q-btn>

        <q-tabs v-model="tab" shrink>
          <q-route-tab to="#getfrog" label="Get Frog" />
          <q-route-tab to="#features" label="Features" />
          <q-route-tab to="#privacy" label="Privacy" />
        </q-tabs>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer reveal class="footer">
      <div class="row justify-center">
        <a
          :class="$q.dark.isActive ? 'text-primary' : 'text-dark'"
          href="https://github.com/tenderowl/frog"
        >
          <q-icon name="eva-github-outline" class="q-mr-xs"></q-icon>GitHub
        </a>
        <a
          :class="$q.dark.isActive ? 'text-primary' : 'text-dark'"
          href="https://tenderowl.com"
        >
          Made by TenderOwl
        </a>
      </div>
    </q-footer>
  </q-layout>
</template>

<script lang="ts" setup>
import { onMounted, ref } from 'vue';
import { useQuasar } from 'quasar';

const $q = useQuasar();
const tab = ref('');

const toggleDarkMode = () => {
  $q.dark.toggle();
  localStorage.setItem('dark-mode', $q.dark.isActive.toString());
};

onMounted(() => {
  $q.dark.set(localStorage.getItem('dark-mode') === 'true');
});
</script>

<style lang="scss">
.header {
  background-color: rgb(251 251 255 / 0.1);
  backdrop-filter: blur(7px);
}

.footer {
  background-color: rgb(251 251 255 / 0.1);
  backdrop-filter: blur(7px);
  padding: 40px;
  position: relative;

  a {
    text-decoration: none;
  }
}
</style>
