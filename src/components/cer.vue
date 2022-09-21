<template>
  <h1>CON LA API DE Options:</h1>
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
  <h2>Evento click con la api de options:</h2>
  <p>potencia {{ potencia }}</p>
  <button @click="upPower(2000)">Aumentar potencia</button>
  <button @click="downPower(2000)">Restar potencia</button>
</template>

<script>
export default {
  components: {},
  //api de options
  data() {
    return {
      name: "Anthony",
      myArray: [
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
      ],
      myObject: {
        name: "Christian Anthony",
        edad: 19,
      },
      potencia: 20,
    };
  },
  methods: {
    upPower(n) {
      console.log(`Aumentando poder ->> ${n}`);
    },
    downPower(n) {
      console.log(`Restando poder ->> ${n}`);
    },
  },
};
</script>

<style>
</style>

