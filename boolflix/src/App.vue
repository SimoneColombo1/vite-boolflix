<script>
import SearchImput from './components/SerachImput.vue';
import TvSeriesList from  './components/TvSeriesList.vue';
import FilmList from './components/FilmList.vue';
import axios from 'axios';
export default {
  components:{
    SearchImput,
    TvSeriesList,
    FilmList
  },
  data() {
    return {
      films : [],
      TvSeries:[]
      
    }
  },
  methods: {
     getFilms(textSearched){
      

// Make a request for a user with a given ID
axios.get('https://api.themoviedb.org/3/search/movie?api_key=91729d2a0cf04e5b98d1a49d7ccbcf73&query=' + textSearched + '&include_adult=true&language=it&page=1')
  .then( (response) => {
    // handle success
    console.log(response.data.results);
    this.films = response.data.results;
  })
  .catch(function (error) {
    // handle error
    console.log(error);
  })
  .finally(function () {
    // always executed
  });
     
     },
 Search(textSearched){
  console.log(textSearched);
  this.getTvSeries(textSearched);
  this.getFilms(textSearched);
 },
 getTvSeries(textSearched){
      

      // Make a request for a user with a given ID
      axios.get('https://api.themoviedb.org/3/search/tv?api_key=91729d2a0cf04e5b98d1a49d7ccbcf73&query=' + textSearched + '&include_adult=true&language=it&page=1')
        .then( (response) => {
          // handle success
          console.log(response.data.results);
          this.TvSeries = response.data.results;
        })
        .catch(function (error) {
          // handle error
          console.log(error);
        })
        .finally(function () {
          // always executed
        });
           
           },

  },
  created() {
   // this.getFilms();
    //this.Search();
    //this.getTvSeries();
  },
 
}

 
</script>

<template>
 <main>
  <ul>
  <FilmList :films="films"/>
  <TvSeriesList :TvSeries="TvSeries"/>
</ul>
  <SearchImput @Searched-Film="Search" />
  
 </main>
   
</template>

<style scoped>

</style>
