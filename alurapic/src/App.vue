<template>
  <div>
    <h1>{{titulo}}</h1>
    <ul v-for="foto of fotos">
      <li><img :src="foto.url" :alt="foto.nome"></li>
    </ul>

  </div>

</template>

<script>
export default {

  data(){

    return{
      titulo: 'Alurapic',
      fotos: [],
    }

  },

  created() {
    alert("Criei um componente");

  }

}
</script>

<style>
</style>
