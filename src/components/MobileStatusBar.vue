<script setup lang="ts">
import { onMounted, onUnmounted, ref } from 'vue'

const time = ref('')
let timer = 0

function updateTime() {
  time.value = new Intl.DateTimeFormat('ru-RU', {
    hour: '2-digit',
    minute: '2-digit',
  }).format(new Date())
}

onMounted(() => {
  updateTime()
  timer = window.setInterval(updateTime, 30_000)
})

onUnmounted(() => window.clearInterval(timer))
</script>

<template>
  <div class="status-bar" aria-hidden="true">
    <span>{{ time }}</span>
    <span class="status-bar__indicators">
      <svg viewBox="0 0 18 14"><path d="M1 13V9m4 4V6m4 7V3m4 10V1" /></svg>
      <svg viewBox="0 0 18 14"><path d="M1 5a12 12 0 0 1 16 0M4 8a7.5 7.5 0 0 1 10 0m-7 3a3 3 0 0 1 4 0M9 13h.01" /></svg>
      <svg viewBox="0 0 22 14"><rect x="1" y="2" width="17" height="10" rx="2" /><path d="M20 5v4M4 5h10v4H4z" /></svg>
    </span>
  </div>
</template>
