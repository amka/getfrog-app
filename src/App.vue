<template>
  <router-view />
</template>

<script lang="ts" setup>
import { onMounted, provide } from 'vue';


onMounted(() => {
  const hasDarkPreference = window.matchMedia('(prefers-color-scheme: dark)').matches;
  provide('dark', hasDarkPreference);
})
</script>
