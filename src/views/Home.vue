<template>
  <div class="home">
    <h1>Home Page!</h1>

    <ProductDescriptionDrawer
    :product="product"
    :active="active.product_drawer"
    v-on:close-product-drawer="closeProductDrawer" />

    <div class="product-card-container">
      <ProductSummaryCard v-for="product in items"
       :key="product.id"
       :product="product"
       v-on:view-product="viewProduct($event)"/>
    </div>
  </div>
</template>

<script>
import items from "../data/item.js";
import ProductSummaryCard from "../components/products/ProductSummaryCard";
import ProductDescriptionDrawer from "../components/products/ProductDescriptionDrawer";


export default {
  name: 'Home',
  components: {
    ProductSummaryCard,
    ProductDescriptionDrawer,
    
  },

  methods:{
    viewProduct(product) {
      this.product=product
      this.active.product_drawer=true
      console.log(this.product)
    }, 

    closeProductDrawer(){
      this.active.product_drawer=false
    }
  },

  data(){
    return {
      items: items,
      product:null,
      active:{
        product_drawer: false
      }
    }
  },

}
</script>


<style lang="scss">

.product-card-container{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>