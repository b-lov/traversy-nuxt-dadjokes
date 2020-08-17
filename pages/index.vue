<template>
  <div>
    <h1>Welcome to the best dad jokes app on the web.</h1>
  </div>
</template>

<script>
  export default {
    head() {
      return {
        title: 'Dad Jokes App',
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