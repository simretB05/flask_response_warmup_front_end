<template>
    <div>
    <div v-for="(poke ,i) in pokemon" :key="i">
       <h2>{{poke[`name`]}}</h2>
       <p>{{poke[`description`]}}</p>
       <img :src="poke[`image_url`]" alt="">

    </div>
</div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
        pokemon:[]
    }
  },
    methods: {
    get_pokemon() {
        axios.request( {
            url: `${process.env.VUE_APP_BASE_DOMAIN}/api/pokemon`,
          
        } ).then( ( response ) =>{
            this.pokemon = response[`data`]
            
          
        } ).catch((error) =>{
            error;
            
        } )
    },
    },
    mounted() {
        this.get_pokemon();
        this.$root.$on("new_pokemon", this.get_pokemon);
        }
      }
</script>

<style scoped>

</style>