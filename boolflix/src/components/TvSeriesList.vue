<script>
export default{
   data() {
    return {
       
    }
   },
props:{
    TvSeries:{
        type:Array,
        required:true
    }
}}
</script>

<template>
<li v-for="(serie, index) in TvSeries" :key="index">

{{ serie.name }}
{{ serie.original_name }}
   {{ serie.original_language }}
   {{ serie.vote_average }}
</li>

</template>


<style scoped>
</style>