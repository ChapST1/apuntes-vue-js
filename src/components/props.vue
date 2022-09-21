<template>
  <h2>HOLA</h2>
  <p>Tu numero de la suerte es : {{ power }}</p>
  <button @click="upPower()">A+</button>
  <button @click="upPower()">A-</button>
</template>

<script>
import { ref } from "vue";
export default {
  props: {
    power: {
      type: Number,
      default: 12,
    },
    upPower: Function,
  },
  setup(props) {
    console.log(props);
    return {};
  },
};
</script>

<style>
</style>