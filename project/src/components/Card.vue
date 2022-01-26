<template>
    <div class="card">
        <h2>{{title}}</h2>
        <img v-bind:src="image" alt="">
        <h3>{{cost}}</h3>
        <p>{{description}}</p>
    </div>
</template>

<script>
export default {
    name:"Card",
    props:{
       title:String,
       image:String,
       cost: String,
       description: String,
   },
};
   
</script>
<style >
.card{
    width: 19rem;
    height: 19rem;
    background-color: royalblue;
    margin: 10px auto;
}
</style>
