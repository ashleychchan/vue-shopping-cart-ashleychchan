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
    width: 9rem;
    font-size: 20px;
    background-color: rgb(231, 207, 162);
    border-radius: 20px;
    color: salmon;
}
</style>
