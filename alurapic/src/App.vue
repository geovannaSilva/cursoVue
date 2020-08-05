<template>
  <div class="corpo">

    <h1 class="centralizado">{{ titulo }}</h1>

    <input type="search" class="filtro" v-on:input="filtro = $event.target.value" placeholder="Filtre por parte do titulo">
   {{filtro}}
    <ul class="lista-fotos">

      <li class="lista-fotos-item" v-for="foto in fotos">

        <meu-painel :titulo="foto.titulo">
          <img id="imagem-responsiva" :src="foto.url" :alt="foto.titulo">
        </meu-painel>

      </li>
    </ul>

  </div>
</template>

<script>
import Painel from './components/shared/painel/painel.vue'

export default {

  components: {

    'meu-painel': Painel
  },

  data () {
    return {
      titulo: 'Alurapic',

      fotos: [],
      filtro: "",
    }
  },
  created() {

    this.$http
      .get('http://localhost:3000/v1/fotos')
      .then(res => res.json())
      .then(fotos => this.fotos = fotos, err => console.log(err));
  }
}
</script>

<style>

.corpo {
  font-family: Helvetica, sans-serif;
  width: 90%;
  margin: 0 auto;
}

.centralizado {
  text-align: center;
}

.lista-fotos {
  list-style: none;
}

.lista-fotos .lista-fotos-item {
  display: inline-block;
}

.filtro {
  display: block;
  width: 100%;
}

#imagem-responsiva {
  padding: 15px auto;
  width: inherit;
}

</style>
