<template>
    <div class="cart">
        <div class="card">
            <div class="card-image">
                <img v-bind:src="image" alt="">
            </div>
       <div class="card-text">
        <h2 class="card-title">{{title}}</h2>
        <h3 class="card-cost">${{cost}}</h3>
        <p class="card-description">{{description}}</p>
        <Button @click="$emit('removeItemFromCart')" > remove </Button>
       </div>
    </div>
    </div>
</template>
<script>
export default {
    name:"Cart",
    props:{
       title:String,
       image:String,
       cost: String,
       description: String,
   },
}
</script>
<style scoped >
.card{
    display: grid;
    grid-template-columns: auto auto ;
    
}
.card{
    width: 30rem;
    height: 8rem;
    background-color: rgb(245, 207, 213);
    margin: 4rem auto;
   
}
img{
    width: 8rem;
    height: 8rem;
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
    margin: .5rem;
}

</style>

