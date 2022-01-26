<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <h1 v-if="graduated">{{student}}</h1>
    <h1 v-else>"stupid"</h1>
<ul>
  <li v-for="animal in animals" :key="animal">{{animal}}
  </li>
</ul>
<button v-on:click="authState" v-if="loggedIn">logout</button>
<button v-on:click="authState" v-else >login</button>
<input type="text" placeholder="edit me" v-model="message">
<p>{{ message }}</p>
<input type="checkbox" id= "jack" value="Jack" v-model="checkedNames"/>
<label for="jack">Jack</label>
<input type="checkbox" id= "john" value="John" v-model="checkedNames"/>
<label for="john">John</label>
<input type="checkbox" id= "mike" value="Mike" v-model="checkedNames"/>
<label for="mike">Mike</label>
<br/>
<span>Checked Names: {{checkedNames}}</span>
<select v-model="selected">
<option >a</option>
<option >b</option>
<option >c</option>
</select>
<span>{{ selected }}</span>
<h2>{{now}}</h2>
<Button>hi</Button>
<Card title="HElllo" description="dfgdfg trsggd" :cost="77"
 image="https://cdn.pixabay.com/photo/2021/07/25/12/22/tourist-attraction-6491734_960_720.jpg"/>
 <Card v-for="destination in destination" :key="destination.name"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Button from "../components/Button.vue";
import Card from "../components/Card.vue";
export default {
  name: 'Home',
  components: {
    Button,
    Card
  },
  data(){
    return {
      student:"harry",
      graduated: false,
      animals: ["doo","poo","ajfj","sgsa"],
      loggedIn: true,
      message:"", 
      checkedNames:[],
      selected:"",
      destinations:[
        {
          name: "Insulin",
          description:"Too bad for you if you have diabetes",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },
        {
          name:"omg"
        }
      ]
    };
  },
  
  methods:{
authState: function(){
  if(this.loggedIn===false){
    this.loggedIn= true;
  } else{
    this.loggedIn= false;
  }
}
  }
}
</script>
<style>
h1{
  color: red;
}
</style>