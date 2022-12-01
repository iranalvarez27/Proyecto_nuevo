<template>
  <div>
    <nav >
      <div>
        <a class="navbar-brand" >UTEC Shop</a> |
            <router-link to="/home">Home</router-link> |
            <router-link to="/registrar">Registrar</router-link> |
            <router-link to="/about">About</router-link>|
            <router-link to="/contact">Contact </router-link>
      </div>
    </nav> 
    <img src="../assets/portada.png" width="1400" height="650" alt="portada" >
    <h2>Inicio de sesión</h2>
    <label>Usuario </label> 
    <input type="text" v-bind:value="nombre_usuario" v-on:input="verificar_nombre"><br>
    <br>
    <label>Contraseña </label>
    <input type="text" v-bind:value="contrasenha" v-on:input="verificar_contrasenha"><br>
    <br>
    <button type="button" class="btn btn-primary" v-on:click="casa">Login</button>
  </div>
 
  <h7>¿No tiene una cuenta?</h7> <br>
  <p><router-link to="/registrar">Registrarse</router-link></p>

  <br><br><br>
  <footer-c></footer-c>

</template>

<script>
import FooterC from '@/components/FooterC.vue'
export default {
  components: {FooterC},
  name: "LoginView",
  data(){
    return{
      nombre_usuario: "",
      contrasenha: ""
    }
  },

  methods: {
    casa(){
      this.$store.dispatch("accion_act_usuario", this.nombre_usuario)
      this.$store.dispatch("accion_act_contra", this.contrasenha)
      this.$router.push('/home')
    },
    verificar_nombre(e){
      this.nombre_usuario = e.target.value
    },
    verificar_contrasenha(e){
      this.contrasenha = e.target.value
    }
    // se supone que se debe verificar si los datos estan en la base de datos mediante flask usando un fetch
  }

}
</script>

<style scoped>
p{
  color:rgb(24, 24, 119)
}
a{
  color:rgb(90, 4, 90)
}
label{
  color:black
}
h2{
  color:black
}
nav{
  background-color:black
}
a{
  color:lavender
}
h5{
  color:black
  
}
p{
  color:black
}
</style>