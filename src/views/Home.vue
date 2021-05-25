<template>
  <div class="home">
    <ProductDescriptionDrawer
        :product="product"
        :active="active.p_drawer"
        v-on:close-product-drawer="closeProductDrawer()"
    />
    <div class="p-cards-container">
      <ProductsSummaryCards
          v-for="product in items"
          :key="product.id"
          :product="product"
          v-on:view-product="viewProduct($event)" />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import items from '../data/items'
import ProductsSummaryCards from '../components/products/ProductSummaryCard'
import ProductDescriptionDrawer from '../components/products/ProductDescriptionDrawer'
export default {
  name: 'Home',
  components: {
    ProductsSummaryCards, ProductDescriptionDrawer
  },
  data() {
    return {
      items: items,
      product: null,
      active: {
        p_drawer: false
      }
    }
  },
  methods: {
    viewProduct(product){
      this.product = product
      this.active.p_drawer = true
    },
    closeProductDrawer(){
      this.active.p_drawer = false
    }
  }
}
</script>
<style lang="scss">
.p-cards-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
