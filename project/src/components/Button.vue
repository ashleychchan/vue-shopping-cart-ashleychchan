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
    font-size: 30px;
    background-color: royalblue;
    border-radius: 20px;
    color: salmon;
}
</style>
