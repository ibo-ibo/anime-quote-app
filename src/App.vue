<template>
  <div>
    <quote-item
      @get-quote="getQuote"
      :anime-character="character"
      :anime-name="name"
      :anime-quote="quote"
    ></quote-item>
  </div>
</template>

<script>
import QuoteItem from "./components/QuoteItem.vue";
export default {
  name: "App",
  components: { QuoteItem },
  data() {
    return {
      name: "",
      quote: "",
      character: "",
    };
  },
  methods: {
    async getQuote() {
      const res = await fetch("https://animechan.vercel.app/api/random");
      const data = await res.json();
      this.name = data.anime;
      this.quote = data.quote;
      this.character = data.character;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-family: "Raleway", sans-serif;
}

body {
  position: relative;
  background-color: #ffa8a8;
  padding: 3rem;
  color: #212529;
}
</style>
