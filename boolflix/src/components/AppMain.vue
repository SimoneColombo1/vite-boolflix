<script>
export default{
    data() {
        return {
            textSearched:"",
        }
    },
    
   
}
</script>
<template>



<div>
    <input type="text" id="search-bar" v-model="textSearched">
    <button @click="$emit('Searched-Film',textSearched)"> Click ME!!</button>
</div>
 
</template>

<style></style>