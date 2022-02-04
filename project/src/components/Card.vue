<template>
    <div class="card">
        <h2 class="card-title">{{title}}</h2>
        <img v-bind:src="image" alt="">
        <h3 class="card-cost">{{cost}}</h3>
        <p class="card-description">{{description}}</p>
        <Button v-on:click="buyNowState" v-if="inCart"> add to cart </Button>
     <Button v-on:click="buyNowState" v-else>remove from cart</Button>
   
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
    width: 30rem;
    height: 30rem;
    background-color: royalblue;
    margin: 4rem auto;
    border-radius: 1rem;
}
img{
    width: 14rem;
    height: 14rem;
    object-fit: cover;
}
.card-title{
    margin: 3rem;
}
Button{
    margin: 1rem;
}

</style>
