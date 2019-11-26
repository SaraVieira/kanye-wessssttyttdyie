Kanye
<template>
  <main>
    <section>
      <h1>Kanye west wisedom</h1>
      <h3 v-if="loading">Getting the quote</h3>
      <h3 v-if="quote">{{quote}}</h3>
    </section>
    <button v-on:click="getQuote">Get another quote</button>
  </main>
</template>

<script>
export default {
  name: "Kanye",
  data() {
    return {
      quote: "",
      loading: false
    };
  },
  methods: {
    getQuote: async function() {
      this.loading = true;
      const data = await fetch("https://api.kanye.rest").then(rsp =>
        rsp.json()
      );
      this.quote = data.quote;
      this.loading = false;
    }
  },
  async mounted() {
    this.getQuote();
  }
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
main {
  width: 80%;
  margin: auto;
  display: grid;
  height: 100vh;
  grid-template-rows: 1fr 200px;
}

button {
  height: 40px;
  align-self: flex-end;
  border: 0;
  background: #ea7d09;
  color: white;
}
</style>
