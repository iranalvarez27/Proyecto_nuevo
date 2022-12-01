<template>
  <nav>
  <router-link to="/home">Home</router-link> |
  <router-link to="/ventas">Ventas</router-link> |
  <router-link to="/about">About</router-link> |
  <router-link to="/contact">Contact</router-link>
  </nav>
  <br><br><br>
  <div>
    <img src="../assets/inventario.jpg" width="200" height="150">
    <br><br><br><br>
    <table class="table table-bordered">
      <thead class="thead-dark">
          <th scope="col">Item</th>
          <th scope="col">Usuario</th>
          <th scope="col">Producto</th>
      <tr v-for="compra, index of compras" v-bind:key="compra"> 
        <td>{{index + 1}}</td>
        <td>{{compra.nombre_usuario}}</td>
        <td>{{compra.nombre_producto}}</td>
      </tr>
      </thead>
    </table>
    
  </div>

</template>

<script>
export default {
  name: "InventarioView",
  data(){
    return{
      compras: [
        {nombre_usuario: "usuario1", nombre_producto: "oreo"},
        {nombre_usuario: "usuario2", nombre_producto: "coca cola"},
        {nombre_usuario: "usuario3", nombre_producto: "sublime"}
      ]
    }
  }
}
</script>

<style scoped>
nav{
  background-color: black;
}
a{
  color:lavender
}
table{
  font-size: large;
  position: "relative";

}
</style>