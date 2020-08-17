<template>
  <div>
    <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke" />
  </div>
</template>

<script>
  import axios from 'axios';

  export default {
    name: 'JokesPage',
    data() {
      return {
        jokes: [],
      };
    },
    async created() {
      const config = {
        headers: {
          Accept: 'application/json',
        },
      };
      try {
        const res = await axios.get('https://icanhazdadjoke.com/search', config);
        this.jokes = res.data.results;
      } catch (err) {
        console.log(err);
      }
    },
    head() {
      return {
        title: 'Jokes',
        meta: [
          {
            hid: 'description',
            name: 'description',
            content: 'the best of the best',
          },
        ],
      };
    },
  };
</script>

<style>
</style>