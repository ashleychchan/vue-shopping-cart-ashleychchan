<template>
    <div class="card">
        <img v-bind:src="image" alt="">
        <h2 class="card-title">{{title}}</h2>
        <h3 class="card-cost">${{cost}}</h3>
        <p class="card-description">{{description}}</p>
        <Button v-on:click="addItemToCart(destination)" > add to cart </Button>
   
    </div>
</template>

<script>
export default {
    name:"card",
    props:{
       title:String,
       image:String,
       cost: String,
       description: String,
   },
   methods:{
       addItemToCart(destination){
console.log(destination);
       }
   }
};
   
</script>
<style >
.card{
    width: 30rem;
    height: 30rem;
    background-color: rgb(245, 207, 213);
    margin: 4rem auto;
   
}
img{
    width: 14rem;
    height: 18rem;
    object-fit: cover;
}
.card-title, .card-cost
{
    margin: 0.3rem 1rem;
    text-align: left;
}
 .card-description{
     margin:  0rem 0rem 0rem 1rem
 }
Button{
    margin: 2.5rem;
}

</style>
