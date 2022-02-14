<template>
    <div>
        <p>this is the cart</p>
        <div class="card">
        <img v-bind:src="image" alt="">
        <h2 class="card-title">{{title}}</h2>
        <h3 class="card-cost">${{cost}}</h3>
        <p class="card-description">{{description}}</p>
        <Button v-on:click="removeItemFromCart(product)" > remove </Button>
   
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
   methods:{
    removeItemFromCart(product){
        this.cart.splice(this.cart.indexOf(product),1);
    }
   }
}
</script>
