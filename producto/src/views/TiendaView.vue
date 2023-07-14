<template>
  <div class="product">  <Product/></div>
  <div>  <ProductR/></div>

</template>

<style>
 .product{
  margin-top: 3%;
 }
</style>
<script>
// @ is an alias to /src
import Product from '@/components/Producto.vue'
import ProductR from '@/components/Relacionados.vue'

export default {
  name: 'ProductoView',
  components: {
    Product,
    ProductR
  }
}
</script>
