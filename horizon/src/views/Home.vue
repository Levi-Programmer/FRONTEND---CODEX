<template>
    <div class="encabezado">
      <img src="@/assets/logito.png" alt="Logo" class="logo">
      <div class="enlaces">
        <router-link to="/about">Acerca de nosotros</router-link>
        <router-link to="/destinos">Destinos</router-link>
        <router-link to="/politicas">Politicas</router-link>
        <button id="botonLogin" class="boton-login" @click="irALogin">Login</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Home',
    methods: {
      irALogin() {
        this.$router.push('/login');
      }
    }
  }
  </script>
  
  <style>
  /* Tus estilos aquí */
  </style>
  