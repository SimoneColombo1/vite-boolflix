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
      TvSeries:[],
      StarRatings:0,
      
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
      
 
  created() {
   // this.getFilms();
    //this.Search();
    //this.getTvSeries();
    
   
  },
 
 

}
}
</script>

<template>
 <header>
 
 <SearchImput @Searched-Film="Search" />
</header>
 <main>
  <ul class="cards-container">
  <FilmList :films="films"/>
  <TvSeriesList :TvSeries="TvSeries"/>
  
</ul>
  
  
 </main>
   
</template>

<style scoped  lang="scss">
@use './styles/general.scss';
@use './styles/partials/mixins';

header{
  background-color: black;
  height: 10vh;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

main{
  background-color: #1b1b1b;
  height: 90vh;
  
  
 
}

.cards-container{
  display: flex;
  flex-direction: row;
  overflow-x: scroll;
  overflow-y: hidden;
  list-style: none;
  padding-top: 9rem;
  height: 700px;
}
</style>
