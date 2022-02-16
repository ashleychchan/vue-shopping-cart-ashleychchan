<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Vegan Repellent</router-link> 
      <router-link to="/about"></router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>
html, body{
 margin: 0;
 padding: 0;
 overflow-x: hidden;
}
body{
  background-color: white;
}
#nav {
  padding: 2rem;
  width: 100%;
  background-color: rgb(232,226,215);
}

#nav a {
  font-weight: bold;
  color: darkgray;
  font-size: 2rem;
  text-decoration: none;
  margin: 1rem;
}

#nav a.router-link-exact-active {
  color: rgb(41,43,131);
  font-size: 4rem;
  justify-content: left;
}

.icon{
  width: 1.4rem;
  height: 1.4rem;
}


</style>
