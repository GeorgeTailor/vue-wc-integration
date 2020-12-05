<template>
  <div id="app">
    <zoo-header headertext="Zoo web components in Vue">
      <img slot="img" alt="Zooplus logo" src="assets/logo.png"/>
    </zoo-header>
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from './components/HelloWorld.vue';
import '@zooplus/zoo-web-components';

@Component({
  components: {
    HelloWorld,
  },
})
export default class App extends Vue {}
</script>

<style lang="css">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
:root {
  --primary-mid: #3c9700;
  --primary-light: #66b100;
  --primary-dark: #286400;
  --primary-ultralight: #ebf4e5;
  --secondary-mid: #ff6200;
  --secondary-light: #f80;
  --secondary-dark: #cc4e00;
  --info-ultralight: #ecf5fa;
  --info-mid: #459fd0;
  --warning-ultralight: #fde8e9;
  --warning-mid: #ed1c24;

  --additional-elements-display: flex;
}
</style>
