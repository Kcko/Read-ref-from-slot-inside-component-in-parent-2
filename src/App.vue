<template>
  <div id="app" ref="testRoot">
    <HelloWorld :test="inputEl" :test2="1" ref="test99">
      <h2>Slot in parent inside Helllo World</h2>
      <input type="text" ref="test1" />
    </HelloWorld>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
  },
  mounted() {
    console.log('Outer: ', this.$refs);
    this.$data.inputEl = this.$refs.test1;
  },
  data() {
    return {
      inputEl: {},
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
