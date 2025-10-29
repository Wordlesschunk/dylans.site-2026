<script setup lang="ts">
defineProps<{
  name: string
  role: string
}>()
</script>

<template>
  <div class="greetings">
    <h1 class="title">{{ name }}</h1>
    <h3 class="subtitle">{{ role }}</h3>

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
.greetings {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  padding: 2rem 1rem;
}

.title {
  font-weight: 600;
  font-size: 2.4rem;
  color: #2ecc71;
  margin: 0;
}

.subtitle {
  font-size: 1.2rem;
  color: #555;
  margin: 0;
}

.icons {
  display: flex;
  gap: 1rem;
  margin-top: 1.5rem;
}

.icon {
  font-size: 1.5rem;
  color: #2c3e50;
  transition: color 0.3s ease, transform 0.2s ease;
}

.icon:hover {
  color: #2ecc71;
  transform: translateY(-3px);
}

@media (min-width: 1024px) {
  .greetings {
    align-items: flex-start;
    text-align: left;
  }
}
</style>
