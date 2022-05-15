<template>
  <h1>Peek A Vue</h1>
  <section class="game-board">
    <Card v-for="(card, idx) in cardList" :value="card" :key="`card-${idx}`" />
  </section>
</template>

<script>
import Card from "./components/Card.vue";

export default {
  name: "App",
  components: {
    Card,
  },
  setup() {
    const cardList = [];
    for (let i = 0; i < 16; i++) {
      cardList.push(i)
    }

    return {
      cardList
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.card {
  border: 5px solid #ccc;
}

.game-board {
  display: grid;
  grid-template-columns: 100px 100px 100px 100px;
  grid-template-rows: 100px 100px 100px 100px;
  column-gap: 30px;
  row-gap: 30px;
  justify-content: center;
}
</style>
