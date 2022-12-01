<template>
  <div>
    <nav>
      <a>
      <router-link to="/registrar_producto">Registrar producto</router-link> |
      <router-link to="/home">Home</router-link>
    </a>
    </nav>
    <br><br>
    <h1>Página de ventas</h1>
    <img src="../assets/vemtas.png" width="200" height="200">
    <br><br><br><br>
    <table class="table table-bordered">
      <tr>
        <th>#</th>
        <th>Nombre</th>
        <th>Tipo</th>
      </tr>
      <tr v-for="producto,index of productos" v-bind:key="producto">
        <td>{{index+1}}</td>
        <td>{{producto.nombre_producto}}</td>
        <td>{{producto.tipo_producto}}</td>
      </tr>
    </table>
  </div>

</template>

<script>
export default {
  name: "VentasView",
  data(){
    return{
      productos: [
        {nombre_producto: "oreo", tipo_producto: "galleta"},
        {nombre_producto: "coca cola", tipo_producto: "gaseosa"},
        {nombre_producto: "sublime", tipo_producto: "chocolate"}
      ]
    }
  }
  // se supone que productos debe contener todos los productos del usuario con el que te has registrado de la base de datos mediante flask
  // usando un fetch y created
}
</script>

<style scoped>
table{
  padding-left: 575px;
}
nav{
  background-color:black
}
a{
  color:lavender
}
h1{
  color: black
}
</style>
