<script setup lang="ts">
defineProps<{
  name: string
  role: string
}>()
</script>

<template>
  <div class="header-text">
    <div class="text">
      <h1 class="title">{{ name }}</h1>
      <h3 class="subtitle">{{ role }}</h3>
    </div>

    <div class="icons">
      <a href="#" aria-label="GitHub" class="icon">
        <i class="fab fa-github"></i>
      </a>
      <a href="#" aria-label="LinkedIn" class="icon">
        <i class="fab fa-linkedin"></i>
      </a>
      <a href="#" aria-label="Twitter" class="icon">
        <i class="fab fa-twitter"></i>
      </a>
    </div>
  </div>
</template>

<style scoped>
.header-text {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 4rem 2rem 2rem 2rem;
}

.text {
  text-align: left;
}

.title {
  font-weight: 600;
  font-size: clamp(2rem, 6vw, 5.4rem);
  color: #2ecc71;
  margin: 0;
}

.subtitle {
  font-size: clamp(1.2rem, 4vw, 3.2rem);
  color: #555;
  margin: 0;
}

.icons {
  display: flex;
  gap: 1rem;
  margin-top: 1rem;
}

.icon {
  font-size: clamp(1.2rem, 2.5vw, 1.5rem);
  color: #2c3e50;
  transition: color 0.3s ease, transform 0.2s ease;
}

.icon:hover {
  color: #2ecc71;
  transform: translateY(-3px);
}

@media (min-width: 1024px) {
  .header-text {
    padding-left: 6rem;
    padding-right: 4rem;
  }
}
</style>
