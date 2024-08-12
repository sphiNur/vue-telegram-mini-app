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
.container {
  font-family: Arial, sans-serif;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  background-color: #f0f2f5;
  text-align: center;
  padding: 20px;
}

button {
  background-color: #0088cc;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
  margin-top: 20px;
}

button:hover {
  background-color: #006699;
}
</style>