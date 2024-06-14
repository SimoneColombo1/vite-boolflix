<script>
import AppMain from './components/AppMain.vue';
import axios from 'axios';
export default {
  components:{
    AppMain
  },
  data() {
    return {
      films : [],
    }
  },
  methods: {
     getFilms(){
      

// Make a request for a user with a given ID
axios.get('https://api.themoviedb.org/3/search/movie?api_key=91729d2a0cf04e5b98d1a49d7ccbcf73&query=i&include_adult=true&language=it&page=1%27')
  .then( (response) => {
    // handle success
    console.log(response.data.results);
    this.films = response.data.results
  })
  .catch(function (error) {
    // handle error
    console.log(error);
  })
  .finally(function () {
    // always executed
  });
     
     }

  },
  created() {
    this.getFilms();
  },
}

 
</script>

<template>
 <main>
  <ul>
    <li v-for="(film, index) in films" :key="index">
{{ film.original_title }}
 {{ film.title }}
    {{ film.original_language }}
    {{ film.vote_average }}
</li>
  </ul>
 </main>
   
</template>

<style scoped>

</style>
