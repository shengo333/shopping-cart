<template>
  <div id="wrapper">
    <ShoppingItem v-for="product in products" :product="product"/>
    <input type="text" v-model="newProduct.title">
    <input type="number" v-model="newProduct.price">
    <button @click="addProduct" >Submit</button>

  </div>
</template>

<script>
import ShoppingItem from './components/ShoppingItem.vue'

export default {
  name: 'App',
  components: {
    ShoppingItem
  },
  data(){
    return{
      newProduct: {
        price: null,
        title: null
        },
      products:[
        {
          title: "jonjoli",
          price: 2,
        },
        {
          title: "ombalo",
          price: 4,
        },
        {
          title: "fortokhali",
          price: 5,
        },
      ],
      }
  },
  methods: {
    addProduct: function () {
        this.products.push(this.newProduct)
      //add product to the object
      alert("product has been added")
    }
  } 
}
</script>

<style>
#wrapper{
  display: flex;
  gap: 3rem;
  justify-content: center;
  align-items: center;
  height: 100vh;
}


</style>
