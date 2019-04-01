<template>
  <div id="app">
    <img src="./assets/2s_stamp.png" alt="Logo">
    <h1>Sopra Steria Chat</h1>
    <input type="text" v-on:keyup.enter="sendMessage" placeholder="Write a message!">
    <transition-group tag="div" class="chat-box" name="slide-down" appear>
      <div
        class="chat-message"
        v-for="message in messages"
        :key="message"
      >
        {{ message }}
      </div>
    </transition-group>
  </div>
</template>

<script>
import Vue from 'vue';
import * as signalR from '@aspnet/signalr';

export default {
  name: 'app',
  components: {
  },
  data() {
    return {
      messages: [],
    };
  },
  // This is called whever the app gets mounted in the DOM
  // (AKA a nice place to place init logic :))
  async mounted() {
    // TODO: Build a hub
    // TODO: Register event handler
    // TODO: Start the hub
  },
  // This is called whenever this component is removed from the DOM
  // (AKA a nice place to destroy stuff you don't want :))
  async beforeDestroy() {
    // TODO: Stop the hub
  },
  methods: {
    async sendMessage(e) {
      // TODO: We need to send a message to the hub
      // TODO: We need to clear the text input after
    },
  },
};
</script>

<style>
html, body {
  padding: 0;
  margin: 0;
  height: 100%;
  overflow: hidden;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
  font-size: 1.5em;
  display: flex;
  flex-direction: column;
  align-items: center;
}

input {
  margin: 1em;
  padding: .5em;
  font-size: 1.5em;
}

.chat-box {
  position: relative;
}

.chat-message {
  text-align: left;
  opacity: 1;
}

.slide-down-enter-active, .slide-down-leave-active, .slide-down-move {
  transition: all .5s ease-in-out;
}

.slide-down-leave-active {
  position: absolute;
}

.slide-down-enter {
  transform: translateY(-1em);
  opacity: 0;
}

.slide-down-leave-to {
  transform: translateY(1em);
  opacity: 0;
}
</style>
