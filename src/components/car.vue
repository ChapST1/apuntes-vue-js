<template>
  <h1>CON LA API DE COMPOSICION:</h1>
  <h1>Mi primer componente</h1>
  <p>Mi primera variable en vue name: {{ name }}</p>
  <p>Mi primer array en vue name: {{ myArray }}</p>
  <p>Filtrar en el mes que estamos: {{ myArray[8] }}</p>
  <p>Mi primer objeto en vue name: {{ myObject }}</p>
  <p>
    filtrar mi nombre y edad : {{ myObject.name }} y tengo
    {{ myObject.edad }} anos
  </p>
  <hr />
  <h2>Recorrer my array:</h2>
  <ul>
    <li v-for="(month, index) in myArray" :key="index">Mes: {{ month }}</li>
  </ul>
  <h2>Filtrar meses:</h2>
  <ul>
    <li v-for="(month, index) in myArray" :key="index">
      <span v-if="month == 'Setiembre'"> Estamos en: {{ month }} </span>
    </li>
  </ul>
  <h2>La forma correcta</h2>
  <ul>
    <template v-for="(month, index) in myArray" :key="index">
      <li v-if="month == 'Setiembre'">Estamos en: {{ month }}</li>
    </template>
  </ul>
  <h2>Evento click con la api de COMPOSICION:</h2>
  <p>Power: {{ power }}</p>
  <button @click="upPower(2000)">poder +</button>
  <button @click="downPower(1000)">poder -</button>

  <h2>PASANDO PROPS ENTRE COMPONENTES:</h2>
</template>

<script>
import { ref } from "vue";
export default {
  components: {},
  setup() {
    const name = "Christian";
    const myArray = [
      "Enero",
      "Febrero",
      "Marzo",
      "Abril",
      "Mayo",
      "Junio",
      "Julio",
      "Agosto",
      "Setiembre",
      "Octubre",
      "Novienbre",
      "Diciembre",
    ];
    const myObject = {
      name: "Christian",
      edad: 19,
    };
    let power = ref(40);
    const upPower = (n) => {
      console.log(`Aumentando poder ${n}`);
      console.log(power.value);
      power.value++;
    };
    const downPower = (n) => {
      console.log(`Restando poder ${n}`);
    };
    return {
      name,
      myArray,
      myObject,
      power,
      upPower,
      downPower,
    };
  },
};
</script>

<style>
</style>