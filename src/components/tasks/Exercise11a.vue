<template>
    <div>
      <p>Celsius: <input v-model="celsius" type="number"></p>
      <p>Fahrenheit: <input v-model="fahrenheit" type="number"></p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        celsius: 0,
      };
    },
    computed: {
      fahrenheit: {
        get() {
          return (this.celsius * 9/5) + 32;
        },
        set(newValue) {
          this.celsius = (newValue - 32) * 5/9;
        },
      },
    },
  };
  </script>