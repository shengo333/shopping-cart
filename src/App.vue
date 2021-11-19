<template>
  <div id="wrapper">
    <ShoppingItem v-for="(product, index) in products" :product="product" :index="index" @removeProduct="removeProduct"/>
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
    addProduct () {
      let newProduct = {
        ...this.newProduct
        
        //title: this.newProduct.title,
        //price: this.newProduct.price
      }
      
      //newProduct.price = this.newProduct.price
      //newProduct.title = this.newProduct.title
      this.products.push(newProduct)
      //add product to the object
      //alert("product has been added")
      this.newProduct.price = null
      this.newProduct.title = null
    },
    removeProduct (index) {
      this.products.splice(index,1)
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
