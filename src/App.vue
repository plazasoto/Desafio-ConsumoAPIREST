<template>
  <div id="app">
    <UserView />
    <ChatView />
    <UserView />
  </div>
</template>

<script>
import UserView from './components/UserView.vue'
import ChatView from './components/ChatView.vue'

export default {
  name: 'App',
  components: {
    UserView,
    ChatView
  }
}
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
