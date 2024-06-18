<script>
import { effect } from 'vue';

export default{
   data() {
    return {
       hover:false
    }
   },
   methods: {
    hoverEffect(){
       this.hover=true;
       console.log(this.hover);
    },
    HoverNone(){
        this.hover=false;
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

    <li v-for="(film, index) in films" :key="index" class="card" @mouseover="hoverEffect(index)" @mouseleave="HoverNone(index)">
      <div class="card-image" :class="(hover === false) ? 'active':'NotActive'" >
        
        <img :src="'http://image.tmdb.org/t/p/w342'+ film.poster_path" :alt="film.title" >
 </div>
 
 <div class="card-elements" :class="(hover === true) ? 'active':'NotActive'" >
   <span> Titolo: {{ film.title }}</span>
    <span>Titolo originale: {{ film.original_title }}</span>
   
    
    <span  v-if="film.original_language==='it'">
        Lingua:<img class="flag" src="../assets/flags/italy-flag-3d-icon-128.png">
    </span>
    <span  v-else-if="film.original_language==='en'">
        Lingua:<img class="flag" src="../assets/flags/united-states-of-america-flag-3d-icon-128.png">
    </span>
    <span  v-else-if="film.original_language==='es'">
        Lingua:<img class="flag" src="../assets/flags/spain-flag-3d-icon-128.png">

    </span>
   <span  v-else-if="film.original_language==='fr'">
    Lingua:<img class="flag" src="../assets/flags/france-flag-3d-icon-128.png">
</span>
   <span  v-else-if="film.original_language==='ja'">
    Lingua:<img class="flag" src="../assets/flags/japan-flag-3d-icon-128.png">
</span>
   <span  v-else="">
    Lingua:<img class="flag" src="../assets/flags/world-flag.png">
   </span>
    <span v-if="film.vote_average /2 > 0.1 && film.vote_average /2 < 0.9"> 
        
        <p>Voto:</p>
        <i class="fa-solid fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
    
    </span>
    <span v-else-if="film.vote_average /2 > 1.1 && film.vote_average /2 < 1.9">
       <p>Voto:</p> 
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
    </span>
    <span v-else-if="film.vote_average /2 > 2.1 && film.vote_average /2 < 2.9">
        Voto:<i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
    </span>
    <span v-else-if="film.vote_average /2 > 3.1 && film.vote_average /2 < 3.9">
        <p>Voto:
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-regular fa-star"></i></p>
    </span>
    <span v-else-if="film.vote_average /2 > 4.1 && film.vote_average /2 < 4.9">
        <p>Voto:<i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i></p>
    </span>
    <span v-else>
        Voto:<i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
        <i class="fa-regular fa-star"></i>
        </span>
      <span>
        Overview:{{ film.overview }}
      </span>
</div>
</li>
  
</template>

<style lang="scss"  scoped>
@use '../styles/partials/mixins' as *;
 
img{
    height: 516px;
}

.active{
    display: flex

}

.NotActive{
    display: none
}


.card-elements{
   
   flex-direction: column;
    width: 344px;
    height: 516px;
    font-size: 1rem;
    color: white;
.flag{
   @include flags();
  
}

.fa-star{
    color: gold;
   
}
span{
    margin-top: 1rem;
}

}

.card{
    margin: 0.5rem;
   

}
</style>