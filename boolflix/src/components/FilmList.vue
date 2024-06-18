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

    <li v-for="(film, index) in films" :key="index">

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
    <span v-if="film.vote_average /2 > 0.1 && film.vote_average /2 < 0.9"> 1</span>
    <span v-else-if="film.vote_average /2 > 1.1 && film.vote_average /2 < 1.9">2</span>
    <span v-else-if="film.vote_average /2 > 2.1 && film.vote_average /2 < 2.9">2</span>
    <span v-else-if="film.vote_average /2 > 3.1 && film.vote_average /2 < 3.9">3</span>
    <span v-else-if="film.vote_average /2 > 4.1 && film.vote_average /2 < 4.9">4</span>
    <span v-else>
        {{ film.vote_average / 2 }}</span>
</li>
  
</template>

<style scoped></style>