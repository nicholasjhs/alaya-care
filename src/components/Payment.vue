<template>
    <div class="payment-container">
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
</template>

<script>

export default {
  name: 'Payment',
  components: {

  },
  data() {
      return {
      }
  },
  props: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>