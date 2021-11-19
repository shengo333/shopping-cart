<template>
    <div class="product" >
      {{product.title}} {{product.price}}
    </div>
</template>

<script>
export default {
  name: 'ShoppingItem',
  props: {
    product: Object,
  },

  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.product {
  border: 1px solid orangered;
  padding: 3rem;
}
</style>
