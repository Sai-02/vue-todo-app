<template>
  <div class="root-app">
    <List />
  </div>
</template>

<script>
import List from "./components/List.vue"
export default {
  name: 'App',
  components: {
    List
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.root-app {
  width: 100vw;
  height: 100vh;
  background: linear-gradient(119deg, #EEF5FF 0%, #F0EEFF 100%);
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
