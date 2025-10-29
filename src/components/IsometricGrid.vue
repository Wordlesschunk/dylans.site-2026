<template>
  <div class="grid">
    <IsometricCard
        v-for="(img, index) in images"
        :key="index"
        :image="img"
    />
  </div>
</template>

<script setup>
import IsometricCard from './Card.vue'

const images = [
  '/path/to/image1.png',
  '/path/to/image2.png',
  '/path/to/image3.png',
  '/path/to/image4.png'
]
</script>

<style scoped>
.grid {
  display: flex;
  flex-wrap: wrap;
  gap: 40px;
  perspective: 1200px;
  justify-content: center;
  align-items: center;
  padding: 50px;
  background: #111;
}
</style>
