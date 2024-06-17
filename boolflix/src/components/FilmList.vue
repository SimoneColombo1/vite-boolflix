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
    
    {{ film.vote_average }}
</li>
  
</template>

<style scoped></style>