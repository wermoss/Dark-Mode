<script setup>
import { useColorMode } from '@vueuse/core'
import IconMoon from './components/IconMoon.vue'
import IconSun from './components/IconSun.vue'

const colorMode = useColorMode()

const toggleMode = () => {
  colorMode.value = colorMode.value === 'dark' ? 'light' : 'dark'
}
</script>

<template>
  <div>
    <button @click="toggleMode" style="display: flex; align-items: center">
      <IconSun v-if="colorMode === 'light'" />
      <IconMoon v-else-if="colorMode === 'dark'" />
      <IconCafe v-else />
    </button>
  </div>
</template>

<style>
.dark {
  background-color: #333;
  color: white;
}
.light {
  background-color: white;
  color: black;
}
</style>
