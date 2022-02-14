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
<Button>cart</Button>
<div class="cart">
  <h1>{{cart.length}} in cart</h1>
  <Cart class="carty"
  v-for="product in cart"
 :key="product.name"
 :image="product.img"
  />
</div>

 <div class="cards">
 <Card class="cardy" v-for="product in products" 
 :key="product.name"
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
      cart:[{
          name: "insulin",
          description:"too bad for you if you have diabetes",
          cost:"88.00",
          img:"https://cdn.pixabay.com/photo/2017/01/11/20/39/insulin-syringe-1972843_960_720.jpg"
        }],
      products:[
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
          img:"https://www.news10.com/wp-content/uploads/sites/64/2022/01/beer.jpg?strip=1&w=640"
        },
        {
          name: "perfume",
          description:"too bad for you if you want to give people asthma attacks",
          cost:"97.00",
          img:"https://m.media-amazon.com/images/I/41VIkN0BOML._SL1037_.jpg"
        },
        {
          name: "plastic bag",
          description:"too bad for you if you want to choke turtles",
          cost:"1 turtlelife ",
          img:"https://www.popsci.com/uploads/2020/10/28/5BTIYSAMBJFPNBSWOHYQW4KKBE.jpg?auto=webp&width=1440&height=1080"
        },
        {
          name: "nail polish",
          description:"too bad for your PLAIN NAILS",
          cost:"15.00",
          img:"https://cdn.shopify.com/s/files/1/2665/7478/products/1-PDP-AW-Bottle-Hand.png?v=1603778658"
        },
        {
          name: "crayon",
          description:"too bad for your inner child",
          cost:"7.00",
          img:"https://shop.crayola.com/dw/image/v2/AALB_PRD/on/demandware.static/-/Sites-crayola-storefront/default/dwdfa66042/images/52-3008_8ct_Crayons_PDP_02.jpg?sw=790&sh=790&sm=fit&sfrm=jpg"
        },
        {
          name: "cake mix",
          description:"too bad for you if you want fluffy cakes",
          cost:"8.00",
          img:"https://i5.walmartimages.com/asr/8b383ecf-736c-46ea-8758-2482639c1180.282e759491d1beeb1a497b4fc52ad75e.png?odnHeight=612&odnWidth=612&odnBg=FFFFFF"
        },
        {
          name: "bagel",
          description:"too bad for you if you like cream cheese",
          cost:"2.00",
          img:"https://cdn.loveandlemons.com/wp-content/uploads/2020/05/bagel-recipe.jpg"
        },
        {
          name: "cigarettes",
          description:"Too bad for you if you want to be cool",
          cost:"25.00",
          img:"https://media-cldnry.s-nbcnews.com/image/upload/newscms/2021_17/3468637/210428-cigarettes-jm-1128.jpg"
        },
        {
          name: "toothpaste",
          description:"Too bad for you if you want clean teeth",
          cost:"11.00",
          img:"https://www.cvs.com/bizcontent/merchandising/productimages/large/35000971593_4.jpg"
        },
        {
          name: "gummy candies",
          description:"Too bad for you want to live life YOLO",
          cost:"3.00",
          img:"https://upload.wikimedia.org/wikipedia/commons/a/a6/Oursons_g%C3%A9latine_march%C3%A9_Rouffignac.jpg"
        },
        {
          name: "hearts for xenotransplantation",
          description:"Too bad for you if you have a broken heart",
          cost:"3300.00",
          img:"https://www.news-medical.net/image.axd?picture=2018%2F12%2Fshutterstock_369086330.jpg"
        },

        {
          name: "sprinkles",
          description:"Too bad for you if you like those delectable crunchy candies",
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
  
  }
}
</script>
<style>
h1{
  color: red;
}
.cards{
    display: flex;
  flex-direction: row;
  flex-flow: wrap;
  justify-content: center;
 margin: 8rem;
}
.cardy{
  margin: 4rem;
  height: 30rem;
  width: 14rem;
}

</style>