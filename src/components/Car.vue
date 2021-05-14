<template>
  <h2>Car - Composition API</h2>
  <p>Marca: {{ brand }}</p>
  <p>Modelo: {{ model }}</p>
  <p>Potencia: {{ power }}</p>
  <!-- <button @click="testPower">Aumentar</button> -->
  <button @click="upPower">Aumentar</button>
  <!-- <button @click="downPower">Disminuir</button> -->
  <button @click="downPowerFn">Disminuir</button>
</template>

<script>
export default {
  props: {
    power: {
      type: Number,
      default: 60,
    },
    upPower: {
      type: Function,
    },
    // downPower: {
    //   type: Function,
    // },
  },
  emits: ["downPower"],
  setup(props, context) {
    const brand = "Audi";
    const model = "A4";

    console.log(props);

    const downPowerFn = () => {
      context.emit("downPower");
    };

    // const testPower = () => {
    //   props.upPower();
    // };

    return {
      brand,
      model,
      downPowerFn,
      //   testPower,
    };
  },
};
</script>

<style></style>
