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
      fotos: [
        {
          url: "https://encrypted-tbn2.gstatic.com/images?q=tbn:ANd9GcTwV4kVzT5McBdGSgqlVeRzubrNH_mOrrkKseDOGFURq20HmsrelEfMU7It",
          nome: "Cachorro"
        },
        {
          url: "https://encrypted-tbn2.gstatic.com/images?q=tbn:ANd9GcTwV4kVzT5McBdGSgqlVeRzubrNH_mOrrkKseDOGFURq20HmsrelEfMU7It",
          nome: "Cachorro2"
        }
      ],
    }

  }

}
</script>

<style>
</style>
