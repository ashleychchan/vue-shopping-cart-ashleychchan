<template>
    <div>
        <h2>{{title}}</h2>
        <img src="" alt="">
        <h3>cost</h3>
        <p>description</p>
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
<style scoped>

</style>
