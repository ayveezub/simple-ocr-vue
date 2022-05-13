<template lang="pug">
main
  Home
</template>

<script setup>
import Home from '@/views/Home.vue'
</script>

<style>
@font-face
  font-family: "Iosevka"
  src: url("@/assets/fonts/iosevka-light.woff2") format("woff2")

body
  background-color: #eee8d5

#app
  font-family: Iosevka, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  font-size: large
  text-align: left
  color: #657b83

main
  display: grid
  grid-template-columns: 1fr min(100%, 65ch) 1fr

main > *
  grid-column: 2
</style>
