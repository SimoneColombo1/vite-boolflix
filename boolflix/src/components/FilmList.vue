<script>
export default{
   data() {
    return {
       
    }
   },
props:{
    films:{
        type:Array,
        required:true
    }
}
  
}

</script>

<template>

    <li v-for="(film, index) in films" :key="index" class="card">
      <div class="card-image">
        <img :src="'http://image.tmdb.org/t/p/w342'+ film.poster_path" :alt="film.title">
 </div>
 <div class="card-elements">
      {{ film.title }}
 {{ film.original_title }}
   
    <span class="flag" v-if="film.original_language==='it'">
        <img src="../assets/flags/italy-flag-3d-icon-128.png">
    </span>
    <span class="flag" v-else-if="film.original_language==='en'">
        <img src="../assets/flags/united-states-of-america-flag-3d-icon-128.png">
    </span>
    <span class="flag" v-else-if="film.original_language==='es'">
        <img src="../assets/flags/spain-flag-3d-icon-128.png">

    </span>
   <span class="flag" v-else-if="film.original_language==='fr'">
    <img src="../assets/flags/france-flag-3d-icon-128.png">
</span>
   <span class="flag" v-else-if="film.original_language==='ja'">
    <img src="../assets/flags/japan-flag-3d-icon-128.png">
</span>
   <span class="flag" v-else="">
    <img src="../assets/flags/world-flag.png">
   </span>
    <span v-if="film.vote_average /2 > 0.1 && film.vote_average /2 < 0.9"> 
        
        <i class="fa-solid fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
    
    </span>
    <span v-else-if="film.vote_average /2 > 1.1 && film.vote_average /2 < 1.9">
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
    </span>
    <span v-else-if="film.vote_average /2 > 2.1 && film.vote_average /2 < 2.9">
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
    </span>
    <span v-else-if="film.vote_average /2 > 3.1 && film.vote_average /2 < 3.9">
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-regular fa-star"></i>
    </span>
    <span v-else-if="film.vote_average /2 > 4.1 && film.vote_average /2 < 4.9">
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
    </span>
    <span v-else>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
        </span>
    
</div>
</li>
  
</template>

<style lang="scss"  scoped>
@use '../styles/partials/mixins' as *;
 
img{
    height: 516px;
}


.flag{
   @include flags();
}

.card{
    margin: 0.5rem;


.card-image{
    &:hover{
        display: none;
    }
}

.card-elements{
    

   display: none;


 &:hover{
    display: flex;
    flex-direction: column;
    width: 300px;
    height: 516px;}
   }
   }
</style>