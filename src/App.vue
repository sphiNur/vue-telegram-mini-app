<template>
  <div class="container">
    <h1>{{ title }}</h1>
    <p>{{ message }}</p>
    <button @click="sendMessage">Send Message</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'Welcome to My Vue Mini App!',
      message: 'This is a simple Telegram Mini App built with Vue and hosted on GitHub.'
    }
  },
  methods: {
    sendMessage() {
      if (window.Telegram && window.Telegram.WebApp) {
        window.Telegram.WebApp.sendData("Hello from Vue Mini App!");
      } else {
        alert("Telegram WebApp is not available");
      }
    }
  },
  mounted() {
    // Initialize the Web App
    if (window.Telegram && window.Telegram.WebApp) {
      window.Telegram.WebApp.ready();
    }
  }
}
</script>

<style scoped>

</style>