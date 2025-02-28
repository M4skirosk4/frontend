<template>
    <div>
      <h1>Los microservicios de Erik</h1>
      <button @click="consultarMicroservicio1">Microservicio 1</button>
      <input type="text" v-model="mensaje1" readonly id = "mv4289398rwq9" />
  
      <button @click="consultarMicroservicio2">Microservicio 2</button>
      <input type="text" v-model="mensaje2" readonly id = "f9n243fqef4wn" />
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        mensaje1: "",
        mensaje2: "",
      };
    },
    methods: {
      async consultarMicroservicio1() {
        const response = await fetch("http://localhost:8081/api/mensaje1");
        this.mensaje1 = await response.text();
      },
      async consultarMicroservicio2() {
        const response = await fetch("http://localhost:8082/api/mensaje2");
        this.mensaje2 = await response.text();
      },
    },
  };
  </script>
  