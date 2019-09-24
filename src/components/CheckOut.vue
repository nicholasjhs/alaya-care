<template>
  <div class="checkout-container">
      <div class="checkout-header">
          <Nav :links="links"/>
      </div>
      <div class="checkout-body row">
          <div class="column checkout-product">
              <product :imageLink="product.image" :productName="product.name" :productPrice="product.price" :productDetails="product.details"></product>
          </div>
          <div class="column checkout-payment">
              <Payment />
          </div>
      </div>
      <div class="checkout-footer">

      </div>
  </div>
</template>

<script>
import Nav from './Nav.vue';
import Product from './Product.vue';
import Payment from './Payment.vue';

export default {
  name: 'CheckOut',
  components: {
      Nav,
      Product,
      Payment
  },
  data() {
      return {
          product: {
              image: "https://via.placeholder.com/150",
              name: "13-inch MacBook Pro - Space Grey",
              price: "1,799.00",
              details: ["Intel Core i5 2.3GHz", "8GB memory", "256GB SSD storage"]
          },
          links: [{name: 'Customer info', active: false}, {name: 'Shipping info', active: false}, {name: 'Payment', active: true}],
      }
  },
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>