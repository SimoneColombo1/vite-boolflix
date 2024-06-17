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
    {{ film.vote_average }}
</li>
  
</template>

<style scoped></style>