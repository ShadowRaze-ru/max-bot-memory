<script setup lang="ts">
import BottomNavigation from './components/BottomNavigation.vue'
import MobileStatusBar from './components/MobileStatusBar.vue'
</script>

<template>
  <main class="app">
    <MobileStatusBar />
    <div class="screen-content">
      <RouterView />
    </div>
    <BottomNavigation />
  </main>
</template>
