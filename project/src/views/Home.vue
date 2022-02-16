<template>
  <div class="home">
    <!-- <h1 v-if="graduated">{{student}}</h1>
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
<span>{{ selected }}</span> -->
<Button>Cart<img class="icon" src="https://cdn-icons-png.flaticon.com/512/263/263142.png" alt=""></Button>
<div class="cart">
  <h1>{{cart.length}} in cart</h1>
  <Cart class="carty"
  v-for="(product, index) in cart"
  @removeItemFromCart="removeItemFromCart(product)" 
 :key="index"
 :image="product.img"
 :title="product.name"
 :quantity="product.quantity"
 :cost="product.cost"/>
 <p> </p>
</div>

 <div class="cards">
 <Card class="cardy" v-for="(product, index) in products"
 @addItemToCart="addItemToCart(product)" 
 :key="index"
 :title="product.name" 
 :description="product.description" 
 :image="product.img"
 :cost="product.cost"/>
 
 </div>

  </div>
</template>

<script>
// @ is an alias to /src
import Button from "../components/Button.vue";
import Card from "../components/Card.vue";
import Cart from '../components/Cart.vue';
export default {
  name: 'Home',
  components: {
    Button,
    Card,
    Cart
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
      cart:[],
      products:[
        {
          quantity:1, 
          id:1, 
          name: "insulin",
          description:"too bad for you if you have diabetes",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        },
        {
           quantity:1,
           id:2, 
          name: "beer",
          description:"too bad for you if are alcoholic",
          cost:"12.00",
          img:"https://www.news10.com/wp-content/uploads/sites/64/2022/01/beer.jpg?strip=1&w=640"
        },
        {
           quantity:1,
           id:3, 
          name: "perfume",
          description:"too bad for you if you want to give people asthma attacks",
          cost:"97.00",
          img:"https://m.media-amazon.com/images/I/41VIkN0BOML._SL1037_.jpg"
        },
        {
           quantity:1,
           id:4, 
          name: "plastic bag",
          description:"too bad for you if you want to choke turtles",
          cost:"1 turtlelife ",
          img:"https://www.popsci.com/uploads/2020/10/28/5BTIYSAMBJFPNBSWOHYQW4KKBE.jpg?auto=webp&width=1440&height=1080"
        },
        {
           quantity:1,
           id:5, 
          name: "nail polish",
          description:"too bad for your PLAIN NAILS",
          cost:"15.00",
          img:"https://cdn.shopify.com/s/files/1/2665/7478/products/1-PDP-AW-Bottle-Hand.png?v=1603778658"
        },
        {
           quantity:1,
           id:6, 
          name: "crayon",
          description:"too bad for your inner child",
          cost:"7.00",
          img:"https://shop.crayola.com/dw/image/v2/AALB_PRD/on/demandware.static/-/Sites-crayola-storefront/default/dwdfa66042/images/52-3008_8ct_Crayons_PDP_02.jpg?sw=790&sh=790&sm=fit&sfrm=jpg"
        },
        {
           quantity:1,
           id:7, 
          name: "cake mix",
          description:"too bad for you if you want fluffy cakes",
          cost:"8.00",
          img:"https://i5.walmartimages.com/asr/8b383ecf-736c-46ea-8758-2482639c1180.282e759491d1beeb1a497b4fc52ad75e.png?odnHeight=612&odnWidth=612&odnBg=FFFFFF"
        },
        {
           quantity:1,
           id:8, 
          name: "bagel",
          description:"too bad for you if you like cream cheese",
          cost:"2.00",
          img:"https://cdn.loveandlemons.com/wp-content/uploads/2020/05/bagel-recipe.jpg"
        },
        {
           quantity:1,
           id:9, 
          name: "cigarettes",
          description:"Too bad for you if you want to be cool",
          cost:"25.00",
          img:"https://media-cldnry.s-nbcnews.com/image/upload/newscms/2021_17/3468637/210428-cigarettes-jm-1128.jpg"
        },
        {
           quantity:1,
           id:10, 
          name: "toothpaste",
          description:"Too bad for you if you want clean teeth",
          cost:"11.00",
          img:"https://www.cvs.com/bizcontent/merchandising/productimages/large/35000971593_4.jpg"
        },
        {
           quantity:1,
           id:11, 
          name: "gummy candies",
          description:"Too bad for you want to live life YOLO",
          cost:"3.00",
          img:"https://upload.wikimedia.org/wikipedia/commons/a/a6/Oursons_g%C3%A9latine_march%C3%A9_Rouffignac.jpg"
        },
        {
           quantity:1,
           id:12, 
          name: "hearts for transplantation",
          description:"Too bad for you if you have a broken heart",
          cost:"3300.00",
          img:"https://www.news-medical.net/image.axd?picture=2018%2F12%2Fshutterstock_369086330.jpg"
        },

        {
           quantity:1,
           id:13, 
          name: "sprinkles",
          description:"Too bad for you if you like these delectable crunchy candies",
          cost:"5.00",
          img:"https://www.wilton.com/dw/image/v2/AAWA_PRD/on/demandware.static/-/Sites-wilton-product-master/default/dw466b587e/images/product/710-0-0438/710-0-0438-Wilton-Rainbow-Sprinkles-Mix-10-oz-A4.jpg?sw=800&sh=800"
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
},
buyNowState: function(){
  if(this.incart===false){
    this.incart= true;
  } else{
    this.incart= false;
  }
  },
    addItemToCart(product){
      let found = this.cart.find(product => this.product.name ==product.name);
console.log(this.cart);
     if(found){
found.quantity++;
     }else{
this.cart.push(product);
     }
      
      
},
  removeItemFromCart(product){
  this.cart.splice(this.cart.indexOf(product),1);
    }
  }
}
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Amiko:wght@400;700&display=swap');
body{
  background-color: rgb(232,226,215);
  font-family: 'Amiko', sans-serif;
}
h1 {
  color: rgb(41,43,131)  ;
}

.cards{
    display: flex;
  flex-direction: row;
  flex-flow: wrap;
  justify-content: center;
 margin: 7rem;
}
.cardy{
  margin: 3rem 4rem;
  height: 30rem;
  width: 14rem;
  
}
.icon{
  width: 3rem;
  height: 3rem;
}

</style>