<script setup lang="ts">
import LandingHeader from "@/components/LandingHeader.vue";
import Divider from "@/components/Divider.vue";
import PortfolioCard from "@/components/PortfolioCard.vue";
</script>

<template>
  <div class="page-container">
    <header>
      <LandingHeader role="Fubs" name="Dylan Jennings"/>
    </header>

    <Divider/>

    <main>
      <PortfolioCard/>
    </main>

    <footer>
      <p>&copy; 2025 Dylan Jennings. All rights reserved.</p>
    </footer>
  </div>
</template>

<style scoped>
.page-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

header {
  padding: 1rem;
  text-align: left;
  margin: 0;
}

main {
  background-color: #212121;
  color: #f0f0f0;
  padding: 1rem;
  flex: 1;
  text-align: left;
}

footer {
  background-color: #121212;
  color: #888;
  padding: 1rem;
  text-align: center;
  font-size: 0.875rem;
  border-top: 1px solid #333;
}
</style>
