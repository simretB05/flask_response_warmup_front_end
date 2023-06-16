<template>
    <div>
        <h2>{{ success_messsage }}</h2>

       <div>
        <label for="name">pokemon name</label>
        <input ref="name_input" type="text"  placeholder=" Pokeomn name">
        <label for="description">Pokemon description</label>
        <input  ref="description_input" type="text"  placeholder=" Pokeomn description">
        <label for="description">Pokemon image</label>
        <input ref="image_url_input" type="text"  placeholder=" Pokeomn image">
        <button @click="post_pokemon">submit</button>
       </div>

    </div>
</template>

<script>
import axios from "axios";

    export default {
        data() {
            return {
            success_messsage: undefined,
            }
    },
    mounted() {
            
    },
    methods: {
        post_pokemon(){

            axios.request( {
                url: `${process.env.VUE_APP_BASE_DOMAIN}/api/pokemon`,

                method: `POST`,
                data: {
                    name: this.$refs["name_input"].value,
                    description: this.$refs["description_input"].value,
                    image_url: this.$refs["image_url_input"].value,
                }
            } ).then( (  ) =>{
                this.success_messsage = " successfully posted pokemon"
                this.$root.$emit("new_pokemon");
            } ).catch( ( error ) => {
                error;

            } )
        }
    }
    }
        
</script>

<style scoped>

</style>