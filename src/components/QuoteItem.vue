<template>
  <div class="quote-wrapper">
    <header>
      <h1>{{ animeName }}</h1>
    </header>
    <div class="quote">
      <p class="quote-text">{{ animeQuote }}</p>
      <p class="quote-character">{{ animeCharacter }}</p>
    </div>
    <button @click="getQuote">Get Quote</button>
  </div>
</template>

<script>
export default {
  props: ["anime-name", "anime-quote", "anime-character"],
  emits: ["get-quote"],
  methods: {
    getQuote() {
      this.$emit("get-quote");
    },
  },
};
</script>

<style scoped>
.quote-wrapper {
  padding: 2rem 1rem;
  margin-top: 50px;
  background-color: #fa5252;
  display: flex;
  flex-direction: column;
}

header {
  margin-bottom: 12px;
  display: flex;
  justify-content: center;
  align-items: center;
}

h1 {
  text-shadow: 2px 2px 3px rgba(0, 0, 0, 0.3);
}

.quote {
  padding: 1rem 1rem;
  margin-bottom: 32px;
}

.quote-text {
  margin-bottom: 12px;
  font-size: 24px;
}

.quote-character {
  color: #f8f9fa;
}

button {
  padding: 1rem 2rem;
  display: flex;
  justify-content: center;
  align-items: center;
  background: none;
  outline: none;
  border: none;
  background-color: #5f3dc4;
  border-radius: 4px;
  font-weight: 500;
  font-size: 18px;
  margin: 0 auto;
  cursor: pointer;
}
button:hover {
  opacity: 0.8;
}
</style>
