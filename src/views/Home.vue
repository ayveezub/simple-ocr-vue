<template lang="pug">
.home
  label.select-image
    | Click To Select Image
    input(
      type='file'
      name='select-image__input'
      accept='.jpg, .jpeg, .png'
      style={opacity: 0}
    )
  label.select-language
    | lang:
    select
      option(value='en+ru') en+ru
  label.recognize-image-button
    | Recognize
  textarea.recognized-text(readonly='true', rows='18')
</template>

<script setup>
import { createWorker } from 'tesseract.js'
const worker = createWorker()
</script>

<style>
.home
  display: grid
  grid-template-areas:
    'select-image select-image select-image'
    'select-language select-language recognize-image-button'
    'recognized-text recognized-text recognized-text'
  border-radius: 10px
  background-color: #eee8d5

label
  display: flex
  align-items: center
  justify-content: center
  height: 2em
  margin: 0.5em
  padding: 0.25em
  border-style: solid
  border-width: thin
  border-radius: 5px

select
  margin: 0.5em

.select-image
  flex-direction: column
  grid-area: select-image
  height: 9em

.select-language
  grid-area: select-language
  border-style: none

.recognize-image-button
  grid-area: recognize-image-button

.recognized-text
  font-family: inherit
  font-size: inherit
  grid-area: recognized-text
  margin: 0.5em
  padding: 0.25em
  border-style: solid
  border-width: thin
  border-radius: 10px
  background-color: #fdf6e3
  resize: none
  overflow-y: scroll
</style>
