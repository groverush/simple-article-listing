<script setup lang="ts">
import './assets/main.css'
import ListItem from './components/ListItem.vue'
import seperator from './assets/Seperator.svg'
</script>

<template>
  <main>
    <h2 class="title">We release interesting articles about technology</h2>
    <img :src="seperator" alt="" />
    <ListItem />
  </main>
</template>

<style scoped>
main {
  margin: 0 auto;

  width: 50%;
  display: flex;
  flex-direction: column;
  gap: 1em;
  justify-content: center;
  align-items: center;
}
.title {
  text-align: center;
  font-size: 1.725rem;
  max-width: 600px;
}
main img {
  width: 20%;
}

@media (max-width: 1024px) {
  main {
    width: 80%;
    padding: 1.52em;
  }
  .title {
    font-size: 1.5rem;
    max-width: 500px;
  }
  main img {
    width: 25%;
  }
}
@media (max-width: 640px) {
  main {
    width: 100%;
  }
}
</style>
