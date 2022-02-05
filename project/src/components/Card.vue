<template>
    <div class="card">
        <h2 class="card-title">{{title}}</h2>
        <img v-bind:src="image" alt="">
        <h3 class="card-cost">$ {{cost}}</h3>
        <p class="card-description">{{description}}</p>
   <Button>add</Button>
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
.card-title, .card-cost
{
    margin: 1rem;
    text-align: left;
}
 .card-description{
     margin:  0rem 0rem 0rem 1rem
 }
Button{
    margin: 2.5rem;
}

</style>
