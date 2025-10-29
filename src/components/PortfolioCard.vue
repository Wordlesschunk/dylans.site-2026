<template>
  <main id="top">
    <div class="cards" id="portfolio">
      <div
          v-for="(card, index) in cards"
          :key="index"
          :class="['card', card.isOpen ? 'open' : 'closed', card.isInactive ? 'is-inactive' : '']"
      >
        <div class="card__summary" @click="toggleCard(index)">
          {{ card.title }}
        </div>
        <div class="card__details">
          {{ card.details }}
        </div>
      </div>
    </div>
  </main>
</template>

<script setup>
import { reactive } from "vue";

const cards = reactive([
  { title: "Project 1", details: "Details about project 1", isOpen: false, isInactive: false },
  { title: "Project 2", details: "Details about project 2", isOpen: false, isInactive: false },
  { title: "Project 3", details: "Details about project 3", isOpen: false, isInactive: false },
  { title: "Project 4", details: "Details about project 4", isOpen: false, isInactive: false },
  { title: "Project 5", details: "Details about project 5", isOpen: false, isInactive: false },
  { title: "Project 6", details: "Details about project 6", isOpen: false, isInactive: false },
]);

function toggleCard(index) {
  const card = cards[index];

  if (!card.isOpen) {
    cards.forEach((c, i) => {
      if (i !== index) {
        c.isOpen = false;
        c.isInactive = true;
      }
    });

    card.isOpen = true;
    card.isInactive = false;
  } else {
    card.isOpen = false;

    cards.forEach((c) => (c.isInactive = false));
  }
}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css?family=Josefin+Slab:300,100,400|Open+Sans:300|Raleway:300|Chivo:300,400,700|Lora:400,400i|Poiret+One");

* {
  box-sizing: border-box;
}

body {
  font-size: 16px;
  height: 100vh;
  background: #f9fafb;
  overflow-y: overlay;
}

::-webkit-scrollbar {
  width: 0.75em;
  background: #f9fafb;
}

::-webkit-scrollbar-track {
  background: #f9fafb;
}

::-webkit-scrollbar-thumb {
  background: hsla(6, 89%, 72%, 0.8);
  border-radius: 0.5em;
}

::-webkit-scrollbar-thumb:hover {
  background: hsla(6, 89%, 72%, 1);
}

main {
  margin: 0 10% 0 10%;
  position: relative;
}

.cards {
  display: flex;
  flex-flow: row wrap;
  padding: 5% 0;
  width: 100%;
}

.card {
  margin: 15px;
  width: calc((100% / 3) - 30px);
  transition: all 0.2s ease-in-out;
}

@media screen and (max-width: 991px) {
  .card {
    width: calc((100% / 2) - 30px);
  }
}

@media screen and (max-width: 767px) {
  .card {
    width: 100%;
  }
}

.card:hover .card__summary {
  background-color: #f78376;
  transform: scale(1.05);
  opacity: 0.8;
}

.card__summary {
  width: 100%;
  padding: calc(100% - 54px) 2em 2em 2em;
  position: relative;
  cursor: pointer;
  background-color: #949fb0;
  opacity: 0.5;
  color: #eceef1;
  font-size: 1.5em;
  text-transform: uppercase;
  text-align: center;
  transition: all 0.3s ease-in-out;
  border-radius: 1%;
}

.card__details {
  transition: all 0.33s ease-in-out;
  background-color: #4a5464;
  width: 100%;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  text-transform: uppercase;
  color: #eceef1;
  font-size: 1.5em;
}

.card.closed .card__details {
  max-height: 0;
  min-height: 0;
  overflow: hidden;
  margin-top: 0;
  opacity: 0;
}

.card.open .card__details {
  max-height: 1000px;
  min-height: 200px;
  overflow: visible;
  margin-top: 30px;
  opacity: 1;
  padding-top: calc(100% - 54px);
}

.card.open .card__summary {
  background-color: #f78376;
  opacity: 1;
  border-radius: 0;
}

.card.is-inactive .card__summary {
  opacity: 0.33;
}

.card.is-inactive:hover .card__summary {
  opacity: 0.75;
}

@media screen and (min-width: 992px) {
  .card:nth-of-type(3n + 2) .card__details {
    margin-left: calc(-100% - 30px);
  }
  .card:nth-of-type(3n + 3) .card__details {
    margin-left: calc(-200% - 60px);
  }
  .card__details {
    width: calc(300% + 60px);
  }
}

@media screen and (min-width: 768px) and (max-width: 991px) {
  .card:nth-of-type(2n) .card__details {
    margin-left: calc(-100% - 30px);
  }
  .card__details {
    width: calc(200% + 30px);
  }
}
</style>
