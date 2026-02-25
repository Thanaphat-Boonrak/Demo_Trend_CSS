<script setup>
import { onMounted, ref } from 'vue'

const allTheme = ['light', 'dark', 'cyberpunk', 'synthwave']

onMounted(() => {
  const theme = localStorage.getItem('theme')
  document.documentElement.setAttribute('data-theme', theme)
})

const changeTheme = (x) => {
  document.documentElement.setAttribute('data-theme', x)
  localStorage.setItem('theme', x)
}
</script>

<template>
  <div class="navbar fixed bg-base-300 shadow-sm z-50">
    <div class="flex-1">
      <a class="btn btn-ghost text-xl">Group สี่ตัวบาท</a>
    </div>
    <div class="flex-none">
      <ul class="menu menu-horizontal px-1">
        <li class="text-2xl"><RouterLink to="/">Home</RouterLink></li>
        <li class="relative z-50">
          <details class="text-2xl">
            <summary>Theme</summary>
            <ul class="absolute right-0 mt-2 w-40 bg-base-100 rounded-box text-lg p-2 shadow-lg">
              <li v-for="theme in allTheme" :key="x">
                <a @click="changeTheme(theme)">
                  {{ theme }}
                </a>
              </li>
            </ul>
          </details>
        </li>
      </ul>
    </div>
  </div>
</template>

<style></style>
