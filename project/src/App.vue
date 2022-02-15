<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Vegan Repellent</router-link> 
      <router-link to="/about">cart <img class="icon" src="https://cdn-icons-png.flaticon.com/512/263/263142.png" alt=""></router-link>
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
}

#nav a {
  font-weight: bold;
  color: darkgray;
  font-size: 2rem;
  text-decoration: none;
  margin: 1rem;
}

#nav a.router-link-exact-active {
  color: purple;
}

.icon{
  width: 1.4rem;
  height: 1.4rem;
}

</style>
