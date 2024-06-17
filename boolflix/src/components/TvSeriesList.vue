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
<span class="flag" v-if="serie.original_language==='it'">
        <img src="../assets/flags/italy-flag-3d-icon-128.png">
    </span>
    <span class="flag" v-else-if="serie.original_language==='en'">
        <img src="../assets/flags/united-states-of-america-flag-3d-icon-128.png">
    </span>
    <span class="flag" v-else-if="serie.original_language==='es'">
        <img src="../assets/flags/spain-flag-3d-icon-128.png">

    </span>
   <span class="flag" v-else-if="serie.original_language==='fr'">
    <img src="../assets/flags/france-flag-3d-icon-128.png">
</span>
   <span class="flag" v-else-if="serie.original_language==='ja'">
    <img src="../assets/flags/japan-flag-3d-icon-128.png">
</span>
   <span class="flag" v-else="">
    <img src="../assets/flags/world-flag.png">
   </span>
   {{ serie.vote_average }}
</li>

</template>


<style scoped>
</style>