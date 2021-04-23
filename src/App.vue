<template>
  <h1>Counter</h1>
  <counter :initialValue="initialValue" />
</template>

<script>
import Counter from './components/Counter.vue';
export default {
  components: {
    Counter,
  },
  data() {
    return {
      initialValue: 10,
    };
  },
};
</script>

<style>
#app Counter {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
