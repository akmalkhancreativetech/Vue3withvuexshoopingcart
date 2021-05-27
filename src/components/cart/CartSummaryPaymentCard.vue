<template>
<div class="cart_item_card">
  <h3>Cart Total: ${{ cart_total }}</h3>
  <button class="v-product-btn">Pay by credit card</button>
</div>
</template>

<script>
export default {
  computed:{
    cart_total() {
      return this.$store.getters.cartTotal
    }
  }
}
</script>