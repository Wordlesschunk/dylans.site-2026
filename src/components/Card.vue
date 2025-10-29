<template>
  <div class="card">
    <img :src="image" alt="Card" />
  </div>
</template>

<script setup>
defineProps({
  image: {
    type: String,
    required: true
  }
})
</script>

<style scoped>
.card {
  width: 300px;
  height: 200px;
  background: #fff;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 20px 40px rgba(0,0,0,0.3);
  transform: rotateX(25deg) rotateY(25deg);
  transition: transform 0.3s, box-shadow 0.3s;
  cursor: pointer;
}

.card:hover {
  transform: rotateX(0deg) rotateY(0deg) translateY(-15px);
  box-shadow: 0 30px 50px rgba(0,0,0,0.4);
}

.card img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
