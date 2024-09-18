<template>
    <div class="main-class">
      <section class="poke-grid">
        <div class="pokemon" v-for="pokemon in pokemones" :key="pokemon.id">
          <img :src="pokemon.imagen" alt="Imagen de pokemon" style="justify-content: center; width: 100px;">
          <h3>{{ pokemon.nombre }}</h3>
          <h3 class=""  :style="{ backgroundColor:pokemon.type_color}">{{ pokemon.type_name }}</h3>
    
        </div>

      </section>
    </div>
  </template>
  
  <script>
  export default {
    name: 'MainContent',
  
    data() {
      return {
        pokemones: [],
       
      };
    },
    created() {
      this.getAllPokemon();
  
    },
  
    methods: {
      async getAllPokemon() {
        const apiUrl = 'https://cobuses.com.co/APIV2/model/pokemon.php?dato=getallpokemon';
        try {
          const response = await this.axios.get(apiUrl);
          this.pokemones = response.data;
          console.log(response.data);
        } catch (error) {
          console.log('Error al hacer la petición', error);
        }
      },
    },
  };
  </script>
  
  
<style scoped>
.main-class{
  display: flex;
    width: 100%;
    height: auto;
}
.poke-grid{

  width: 70%;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(100px, 7fr));
  gap: 30px;
  padding: 10px;
}
.poke-grid img{
  width: 90%;
 height: 70%;
 
 object-fit: cover;
}
</style>