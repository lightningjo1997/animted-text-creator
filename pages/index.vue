<template>
      <div>
        <h1>Promo Video Maker</h1>
        <textarea v-model="script" placeholder="Paste your script here..."></textarea>
        <button @click="generateSlides">Generate Slides</button>
        <div v-if="slides.length">
          <h2>Preview</h2>
          <div v-for="(slide, index) in slides" :key="index" class="slide">
            <p>{{ slide }}</p>
          </div>
        </div>
      </div>
    </template>

    <script setup>
    import { ref } from 'vue'

    const script = ref('')
    const slides = ref([])

    const generateSlides = () => {
      slides.value = script.value.split('\n').filter(line => line.trim() !== '')
    }
    </script>

    <style>
    .slide {
      margin: 20px 0;
      padding: 20px;
      border: 1px solid #ccc;
      border-radius: 8px;
      background-color: #f9f9f9;
    }
    </style>
