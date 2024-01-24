<template>
    <div id="app">
      <form @submit.prevent="submitForm">
        <div>
          <label for="nombre">Nombre:</label>
          <input type="text" v-model="formData.nombre" required />
        </div>
        <div>
          <label for="tipoDocumento">Tipo de Documento:</label>
          <select v-model="formData.tipoDocumento" required>
            <option value="cedula">Cédula</option>
            <option value="tarjetaIdentidad">Tarjeta de Identidad</option>
          </select>
        </div>
        <div>
          <label for="numeroDocumento">Número de Documento:</label>
          <input type="text" v-model="formData.numeroDocumento" required />
        </div>
        <div>
          <label for="edad">Edad:</label>
          <input type="number" v-model="formData.edad" required />
        </div>
        <div>
          <label for="fechaNacimiento">Fecha de Nacimiento:</label>
          <input type="date" v-model="formData.fechaNacimiento" required />
        </div>
        <div>
          <label for="lugarNacimiento">Lugar de Nacimiento:</label>
          <input type="text" v-model="formData.lugarNacimiento" required />
        </div>
        <div>
          <label for="direccion">Dirección:</label>
          <input type="text" v-model="formData.direccion" required />
        </div>
        <div>
          <label for="email">Email:</label>
          <input type="email" v-model="formData.email" required />
        </div>
        <div>
          <label for="password">Contraseña:</label>
          <input type="password" v-model="formData.password" required />
        </div>
        <div>
          <label for="confirmPassword">Confirmar Contraseña:</label>
          <input type="password" v-model="formData.confirmPassword" required />
        </div>
        <button type="submit">Enviar</button>
      </form>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    // ...
    methods: {
      submitForm() {
        axios.post('http://localhost:8000/api/form-submit/', this.formData)
          .then(response => {
            console.log('Respuesta del servidor:', response);
          })
          .catch(error => {
            console.error('Error:', error);
          });
      }
    }
  };
  </script>
  
  <style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  
  form {
    max-width: 400px;
    margin: 0 auto;
  }
  
  label {
    display: block;
    margin-bottom: 5px;
  }
  
  input,
  select {
    width: 100%;
    padding: 8px;
    margin-bottom: 10px;
  }
  
  button {
    padding: 10px;
    background-color: #3498db;
    color: #fff;
    border: none;
    cursor: pointer;
  }
  </style>