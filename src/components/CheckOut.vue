<template>
  <div class="checkout-container">
      <div class="checkout-header">
          <nav class="checkout-nav">
              <ul class="nav-links">
                  <li class="nav-item">
                      <a href="#">Customer Info</a>
                  </li>
                  <li class="nav-item">
                      <a href="#">Shipping Info</a>
                  </li>
                  <li class="nav-item">
                      <a href="#">Payment</a>
                  </li>
              </ul>
          </nav>
      </div>
      <div class="checkout-body">
          <div class="checkout-product">
              <img class="product-image" src="https://via.placeholder.com/150">
              <h5 class="">13-inch MacBook Pro - Space Grey</h5>
              <p class="">To pay</p>
              <h2 class="">1,799.00 <span>USD</span></h2>
              <ul class="product-details">
                  <li>Intel Core i5 2.3GHz</li>
                  <li>8GB memory</li>
                  <li>256GB SSD storage</li>
              </ul>

          </div>
          <div class="checkout-details">
              <h2 class="">Payment Details</h2>
              <h5 class="">Fill in the info below to continue</h5>
              <form>
                  <div class="cc-number">
                      <label for="ccnums">Creditcard number</label>
                      <input type="text" id="ccnums" name="ccnums" placeholder="0000 0000 0000 0000">
                  </div>
                  <div class="cc-name">
                      <label for="ccname">Cardholer name</label>
                      <input type="text" id="ccname" name="ccname" placeholder="">
                  </div>
                  <div class="cc-expiry">
                    <label for="ccmonth">Expiry month</label>
                    <input type="text" id="ccmonth" name="ccmonth" placeholder="">
                    <label for="ccyear">Expiry year</label>
                    <input type="text" id="ccyear" name="ccyear" placeholder="">
                    <label for="cvv">CVV</label>
                    <input type="text" id="cvv" name="cvv" placeholder="">
                  </div>
                  <button>Checkout</button>
              </form>
          </div>
      </div>
      <div class="checkout-footer">

      </div>
  </div>
</template>

<script>
export default {
  name: 'CheckOut',
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>