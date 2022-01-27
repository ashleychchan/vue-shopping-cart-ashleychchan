<template>
  <div class="home">
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
<!-- <Card title="HElllo" description="dfgdfg trsggd" :cost="77"
 image="https://cdn.pixabay.com/photo/2021/07/25/12/22/tourist-attraction-6491734_960_720.jpg"/> -->
 <Card v-for="destination in destinations" :key="destination.name"
 :title="destination.name" />
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
          name: "insulin",
          description:"too bad for you if you have diabetes",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },
        {
          name: "beer",
          description:"too bad for you if are alcoholic",
          cost:"12.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },
        {
          name: "perfume",
          description:"too bad for you if you want to give people asthma attacks",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },
        {
          name: "plastic bags",
          description:"too bad for you if you want to choke turtles",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },
        {
          name: "nail polish",
          description:"too bad for your PLAIN NAILS",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },
        {
          name: "crayon",
          description:"too bad for your inner child",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },
        {
          name: "cake mixes",
          description:"too bad for you if you want fluffy cow cakes",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },
        {
          name: "bagels",
          description:"too bad for you if you like cream cheese",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },
        {
          name: "cigarettes",
          description:"Too bad for you if you want to be cool",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },
        {
          name: "toothpaste",
          description:"Too bad for you if you want clean teeth",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },
        {
          name: "gummy candies",
          description:"Too bad for you want to live life YOLO",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },
        {
          name: "hearts xenotransplantation",
          description:"Too bad for you if you have a broken heart",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },

        {
          name: "Insulin",
          description:"Too bad for you if you have diabetes",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },
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