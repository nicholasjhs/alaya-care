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
                      <a class="active" href="#">Payment</a>
                  </li>
              </ul>
          </nav>
      </div>
      <div class="checkout-body row">
          <div class="column checkout-product">
              <div class="product-header">
                <img class="product-image" src="https://via.placeholder.com/150">
                <h3 class="product-title">13-inch MacBook Pro - Space Grey</h3>
              </div>
              <div class="product-body">
                <p class="to-pay">To pay</p>
                <h2 class="product-price">1,799.00 <span>USD</span></h2>
                <ul class="product-details">
                    <li class="product-item">Intel Core i5 2.3GHz</li>
                    <li class="product-item">8GB memory</li>
                    <li class="product-item">256GB SSD storage</li>
                </ul>
              </div>

          </div>
          <div class="column checkout-payment">
              <div class="payment-header">
                <h1 class="payment-title">Payment details</h1>
                <h3 class="payment-subtitle">Fill in the info below to continue</h3>
              </div>
              <div class="payment-body">
                <form class="form">
                    <div class="cc-number form-group">
                        <label class="form-label" for="ccnums">Creditcard number</label>
                        <input class="form-input" type="text" id="ccnums" name="ccnums" placeholder="4242 4242 4242 4242">
                    </div>
                    <div class="cc-name form-group">
                        <label class="form-label" for="ccname">Cardholder name</label>
                        <input class="form-input" type="text" id="ccname" name="ccname" placeholder="">
                    </div>
                    <div class="cc-expiry">
                        <div class="form-group">
                            <label class="form-label" for="ccexpiry">Expiry date (MM/YY)</label>
                            <input class="form-input" type="text" id="ccexpiry" name="ccexpiry" placeholder="">
                        </div>
                        <div class="form-group">
                            <label class="form-label" for="cvv">CVV</label>
                            <input class="form-input" type="text" id="cvv" name="cvv" placeholder="">
                        </div>
                    </div>
                    <button class="form-btn">Checkout</button>
                </form>
              </div>
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