<template>
  <h1>Hola Mundo desde VUE JS</h1>
  <h2>Custom event emit</h2>
  <!--   <car /> -->
  <!--  <hr />
  <cer /> -->
  <props :power="power" :upPower="upPower" />
</template>

<script>
import { ref } from "vue";
/* import car from "./components/car.vue"; */
/* import cer from "./components/cer.vue"; */
import props from "./components/props.vue";
export default {
  components: {
    /* car, */
    /* cer, */
    props,
  },
  setup() {
    let power = ref(43);
    const upPower = () => {
      power.value++;
      console.log("Aumentando poder...");
    };
    const downPower = () => {
      power.value++;
      console.log("Aumentando poder...");
    };
    return {
      power,
      upPower,
      downPower,
    };
  },
};
</script>

<style>
</style>