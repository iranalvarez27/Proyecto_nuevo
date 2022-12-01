<template>
    <nav>
        <a></a><router-link to="/home">Home</router-link> |
        <router-link to="/about">About</router-link>  
    </nav>

    <h1>UTEC Shop Contact Information</h1>
    <li>Email: grupo@utec.edu.pe</li>
    <li>Phone: 9999999999</li>
    <box>Message Us</box>
</template>

<script>
export default{
    name:'ContactView'
}
</script>

<style scoped>
h1{
    color:black
}
nav{
    background-color:black
}
a{
    color:lavender
}
</style>