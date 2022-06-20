

<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="header">
      <q-toolbar :class="$q.dark.isActive ? 'text-primary' : 'text-dark'">
        <q-toolbar-title>
          <q-btn href="/" flat stretch>
            Frog
          </q-btn>
        </q-toolbar-title>

        <q-btn @click="toggleDarkMode" flat round dense
          :icon="$q.dark.isActive ? 'eva-sun-outline' : 'eva-moon-outline'" class="q-mr-md">
          <q-tooltip>Toggle Dark Mode</q-tooltip>
        </q-btn>

        <q-tabs v-model="tab" shrink class="gt-xs">
          <q-route-tab href="#getfrog" label="Get Frog" />
          <q-route-tab href="#features" label="Features" />
          <q-route-tab href="#privacy" label="Privacy" />
        </q-tabs>

        <q-btn :class="$q.dark.isActive ? 'text-primary' : 'text-dark'" flat round icon="eva-menu-outline" class="xs">
          <q-menu>
            <q-list style="min-width: 200px">
              <q-item href="#getfrog" clickable v-close-popup>
                <q-item-section>Get Frog</q-item-section>
              </q-item>
              <q-item href="#features" clickable v-close-popup>
                <q-item-section>Features</q-item-section>
              </q-item>
              <q-item href="#privacy" clickable v-close-popup>
                <q-item-section>Privacy</q-item-section>
              </q-item>
            </q-list>
          </q-menu>
        </q-btn>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer reveal class="footer">
      <div class="row justify-center">
        <a :class="$q.dark.isActive ? 'text-primary' : 'text-dark'" href="https://tenderowl.com" class="q-pa-md">
          Made by 🦉 TenderOwl
        </a>
        <a :class="$q.dark.isActive ? 'text-primary' : 'text-dark'" href="https://github.com/tenderowl/frog"
          class="q-pa-md">
          <q-icon name="eva-github-outline" class="q-mr-xs"></q-icon>GitHub
        </a>
      </div>
    </q-footer>
  </q-layout>
</template>

<script lang="ts" setup>
import { onMounted, ref, inject } from 'vue';
import { useQuasar } from 'quasar';

const $q = useQuasar();
const tab = ref('');
const hasDarkPreference = inject('dark');

const toggleDarkMode = () => {
  $q.dark.toggle();
  localStorage.setItem('dark-mode', $q.dark.isActive.toString());
};

onMounted(() => {
  if (localStorage.getItem('dark-mode') == null && hasDarkPreference) {
    $q.dark.set(true);
  } else {
    $q.dark.set(localStorage.getItem('dark-mode') === 'true');
  }
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
