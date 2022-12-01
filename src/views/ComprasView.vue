<template>
  <div class="compras">
    <nav>
      <a><router-link to="/home">Home</router-link></a>
    </nav>
    <h1>Página de compras</h1>
    <img src="../assets/compras.gif" width="400" height="200">
    <br><br><br><br>
    <table>
      <tr v-for="producto of productos" v-bind:key="producto">
        <div class="card" style="width: 18rem;">
          <div class="card-body">
            <a>Nombre: <td  v-if="producto.nombre_usuario !== $store.state.mi_usuario">{{producto.nombre_producto}}</td></a> <br>
            <a>Tipo: <td  v-if="producto.nombre_usuario !== $store.state.mi_usuario">{{producto.tipo_producto}}</td></a><br>
            <button class="btn btn-success" v-on:click="comprar(producto.codigo)">Comprar</button>
          </div>
        </div>
  
        <td></td>
      </tr>
    </table>
  </div>
  <br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
  <footer-c></footer-c>

</template>

<script>
import FooterC from '@/components/FooterC.vue'
export default {
  components: {FooterC},
  name: "ComprasView",
  data(){
    return{
      productos: [
        {nombre_producto: "glasita", tipo_producto: "galleta"},
        {nombre_producto: "inca cola", tipo_producto: "gaseosa"},
        {nombre_producto: "princesa", tipo_producto: "chocolate"}
      ],
      comprado: ""
    }
  },
  methods: {
    comprar(p){
      this.comprado = p
      // se supone que la función debe crear una compra con los datos del producto seleccionado,
      // asignarlos a comprado y guardarlo en la base de datos mediante flask usando un fetch
    }
  }
  // se supone que productos debe contener todos los productos registrados de la base de datos mediante flask
  // usando un fetch y created, se debe filtrar en el template los productos que no sean del usuario con el que
  // te acabas de logear
}
</script>

<style scoped>
nav{
  background-color:black
}
a{
  color:lavender
}
h1{
  color:rgb(18, 18, 18)
}

</style>