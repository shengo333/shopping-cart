<template>
    <div class="product" :class="product.price > 10 ? 'expensive' : '' ">
      {{product.title}} ₾{{product.price}}
      <button @click="removeProduct">Remove </button>
    </div>
</template>

<script>
export default {
  name: 'ShoppingItem',
  props: {
    product: Object,
    index: Number,
  },
  methods: {
    removeProduct(){
      this.$emit("removeProduct", this.index)
    }
  }

  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.product {
  border: 2px solid rgb(122, 122, 124);
  padding: 3rem;
  font-family: sans-serif;
  border-radius: 5px;
}
.expensive{
  background-color: red;
}
</style>
