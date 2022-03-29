<template>
  <div>
    <h1>¿Quién es este pokémon?</h1>

    <PokemonPicture :pokemonId="4" :showPokemon="true"/>
    <PokemonOptions :pokemons="pokemonArr"/>
  </div>
</template>

<script>
import PokemonPicture from '@/components/PokemonPicture'
import PokemonOptions from '@/components/PokemonOptions'

import getPokemonOptions from '@/helpers/getPokemonOptions'

export default {
  components: { PokemonPicture, PokemonOptions},
  data() {
    return {
      pokemonArr: []
    }
  },
  methods: {
    async mixPokemonArray() {
      this.pokemonArr = await getPokemonOptions()
    }
  },
  mounted(){
    this.mixPokemonArray()
  }
}
</script>