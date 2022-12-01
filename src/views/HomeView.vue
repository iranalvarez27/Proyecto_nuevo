<template>
  <div class="home">
    <nav>
    <router-link to="/compras">
      <a>Comprar</a></router-link> |
    <router-link to="/ventas">Vender</router-link> |
    <router-link to="/inventario">Inventario</router-link> |
    <router-link to="/">Logout</router-link>
    </nav>

    <h1>"Bienvenido a UTEC Shop"</h1>
    <br>
    <div v-for="usuario of usuarios" v-bind:key="usuario">
      <h2 v-if="usuario.nombre_usuario === $store.state.mi_usuario">Usuario: {{usuario.nombre_usuario}}</h2>
      <h2 v-if="usuario.contrasenha === $store.state.mi_contrasenha">Contraseña: {{usuario.contrasenha}}</h2>
  </div>
  <br>
  <img src="../assets/shop.jpg" width="1500">
  <br>
  <h6>Valido para Perú. Recibe tus pedidos con la primera entrega totalente gratis</h6>
  </div>


  <footer-c msg=""></footer-c>
</template>

<script>
import FooterC from '@/components/FooterC.vue'
export default {
  components: {FooterC},
  name: 'HomeView',
  data(){
    return{
      usuarios: [
        {nombre_usuario: "usuario1", contrasenha: "a101010a"},
        {nombre_usuario: "usuario2", contrasenha: "b202020b"},
        {nombre_usuario: "usuario3", contrasenha: "c303030c"}
      ]
    }
  }
  // se supone que usuarios debe contener todos los usuarios registrados recibiendolos de la base de datos
  // mediante flask usando un fetch y created
  // se debe filtrar en el template el usuario con el que te acabas de logear o registrar

}
</script>

<style scoped>
nav{
  background-color:black;

}
a{
  color:lavender;
}
</style>
