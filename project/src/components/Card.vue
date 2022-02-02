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
       cost: Number,
       description: String,
   },
};
   
</script>
<style >
.card{
    width: 20rem;
    height: 20rem;
    background-color: royalblue;
    margin: 4rem auto;
}
img{
    width: 10rem;
    height: 10rem;
    object-fit: cover;
}
</style>
