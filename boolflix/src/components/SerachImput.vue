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

<span> BOOLFLIX </span>

<div>
    <input type="text" id="search-bar" v-model="textSearched">
    <button @click="$emit('Searched-Film',textSearched)"> Click ME!!</button>
</div>

</template>

<style scoped>

span{
    color: red;
    font-size: 4rem;
    padding-left: 1rem;
}

input{
    border: solid 2px red;
    border-radius: 4%;
   background-color: #1b1b1b;
   color: white;
   height: 1.5rem;
}

button{
    border: 0;
    background-color: red;
    border-radius: 4%;
    margin: 2rem;
    height: 1.8rem;
    width: 6rem;
    color: white;
    
&:hover{
    background-color: white;
    color: red;
}
}
</style>