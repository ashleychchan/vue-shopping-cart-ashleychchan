<template>
    <button><slot></slot></button>
</template>
<script>
export default {
name: "Button",
};
</script>
<style>
button{
    width: 8rem;
    font-size: 20px;
    background-color: rgb(239,78,66);
    color: white;
    border: none;
}
</style>
