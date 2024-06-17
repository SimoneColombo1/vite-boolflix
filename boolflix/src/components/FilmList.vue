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
    {{ film.original_language }}
    <span v-if="film.original_language==='it'">italiano</span>
    <span v-else-if="film.original_language==='en'">inglese</span>
    <span v-else-if="film.original_language==='es'">spagnolo </span>
   <span v-else-if="film.original_language==='fr'">francia</span>
   <span v-else-if="film.original_language==='ja'">Giappone</span>
   <span v-else="">mondo</span>
    
    {{ film.vote_average }}
</li>
  
</template>

<style scoped></style>