<template>
  <div class="product-container">
      <div class="product-header">
          <img class="product-image" :src="imageLink">
          <h3 class="product-title">{{ productName }}</h3>
      </div>
      <div class="product-body">
          <p class="to-pay">To pay</p>
          <h2 class="product-price">{{ productPrice }} <span>USD</span></h2>
          <ul class="product-details">
              <li class="product-item" v-for="(detail, index) in productDetails" v-bind:key="index">{{ detail }}</li>
          </ul>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Product',
  props: {
      imageLink: {
          type: String,
          required: true,
          default: ""
      },
      productName: {
          type: String,
          required: true
      },
      productPrice: {
          type: String,
          required: true
      },
      productDetails: {
          type: Array,
          required: false,
          default: []
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>