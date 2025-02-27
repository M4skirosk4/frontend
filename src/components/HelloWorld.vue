<template>
    <div>
      <h1>{{ msg }}</h1>
      <button @click="consultarMicroservicio1">Obtener mensaje de Microservicio 1</button>
      <button @click="consultarMicroservicio2">Obtener mensaje de Microservicio 2</button>
      <p>{{ response }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      msg: String
    },
    data() {
      return {
        response: ''
      }
    },
    methods: {
      consultarMicroservicio1() {
        fetch('http://localhost:8081/api/mensaje1')
          .then(response => response.text())
          .then(data => {
            this.response = data
          })
          .catch(error => {
            console.error("Error al obtener mensaje de Microservicio 1:", error);
            this.response = 'Error al obtener mensaje de Microservicio 1';
          });
      },
      consultarMicroservicio2() {
        fetch('http://localhost:8082/api/mensaje2')
          .then(response => response.text())
          .then(data => {
            this.response = data
          })
          .catch(error => {
            console.error("Error al obtener mensaje de Microservicio 2:", error);
            this.response = 'Error al obtener mensaje de Microservicio 2';
          });
      }
    }
  }
  </script>