<template>
  <p>Initial value: {{ initialValue }}</p>
  <p>Actual value: {{ count }}</p>
  <p>Triple value: {{ triple }}</p>
  <button @click="increment">+</button>
  <button @click="decrement">-</button>
</template>

<script>
import { ref, computed, watch, onMounted } from 'vue';

export default {
  name: 'Counter',
  props: {
    initialValue: Number,
  },
  setup(props) {
    const count = ref(props.initialValue);
    const triple = computed(() => count.value * 3);

    const increment = () => {
      count.value++;
    };

    const decrement = () => {
      count.value--;
    };

    watch(count, (newValue, oldValue) => {
      console.log(`Old Value ${oldValue} New Value ${newValue}`);
    });

    onMounted(() => {
      console.log('on mounted');
    });

    return { count, increment, decrement, triple };
  },
};
</script>

<style scoped></style>
