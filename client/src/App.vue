<template>
  <div>
    <NavbarC class="encabezado" />
    <router-view />
    <FooterC class="footer"/>
  </div>
</template>



<script>
import NavbarC from './components/NavbarC.vue';
import FooterC from './components/FooterC.vue';

export default {
  components: {
    NavbarC,
    FooterC
}  
}
</script>

<style>
  @import 'styles/MainS.css'
</style>
