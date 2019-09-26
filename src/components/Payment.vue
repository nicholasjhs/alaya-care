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
                <input class="form-input" type="text" id="ccnums" name="ccnums" v-model.lazy="$v.ccForm.num.$model" placeholder="4242424242424242">
                <div v-if="errors" class="error">
                    <p v-if="!$v.ccForm.num.required">field is required</p>
                    <p v-if="!$v.ccForm.num.minLength || !$v.ccForm.num.maxLength">field must be 16 characters. Remove spaces if present.</p>
                    <p v-if="!$v.ccForm.num.numeric">field can only contain digits from 0-9</p>
                </div>
            </div>
            <div class="cc-name form-group">
                <label class="form-label" for="ccname">Cardholder name</label>
                <input class="form-input" type="text" id="ccname" name="ccname" v-model.lazy="$v.ccForm.name.$model" placeholder="">
                <div v-if="errors" class="error">
                    <p v-if="!$v.ccForm.name.required">field is required</p>
                    <p v-if="!$v.ccForm.name.isFormat">field can only contain alphabet and special characters</p>
                </div>
            </div>
            <div class="cc-expiry">
                <div class="form-group">
                    <label class="form-label" for="ccexpiry">Expiry date (MM/YY)</label>
                    <input class="form-input" type="text" id="ccexpiry" name="ccexpiry" v-model.lazy="$v.ccForm.expiry.$model" placeholder="">
                    <div v-if="errors" class="error">
                        <p v-if="!$v.ccForm.expiry.required">field is required</p>
                        <p v-if="!$v.ccForm.expiry.isGoodFormat">field must have format MM/YY</p>
                    </div>
                </div>
                <div class="form-group">
                    <label class="form-label" for="cvv">CVV</label>
                    <input class="form-input" type="text" id="cvv" name="cvv" v-model.lazy="$v.ccForm.cvv.$model" placeholder="">
                    <div v-if="errors" class="error">
                        <p v-if="!$v.ccForm.cvv.required">field is required</p>
                        <p v-if="!$v.ccForm.cvv.minLength || !$v.ccForm.cvv.maxLength">Field must be 3 characters</p>
                        <p v-if="!$v.ccForm.cvv.numeric">field can only contain digits from 0-9</p>
                    </div>
                </div>
            </div>
        </form>
        </div>
        <div class="payment-footer">
            <button @click.prevent="submit" class="form-btn">Checkout</button>
            <p v-if="errors" class="error">Form has some errors, please correct them.</p>
            <p v-else-if="isSuccessfulSubmit" class="success">Form has been submitted !</p>
        </div>
    </div>
</template>

<script>
import { required, minLength, maxLength, numeric } from 'vuelidate/lib/validators'

export default {
  name: 'Payment',
  components: {


  },
  data() {
      return {
          errors: false,
          isSuccessfulSubmit: false,
          isTouched: false,
          ccForm: {
              num: null,
              name: null,
              expiry: null,
              cvv: null,
          }

      }
  },
  validations: {
      ccForm : {
          num: {
              required,
              numeric,
              minLength: minLength(16),
              maxLength: maxLength(16),
          },
          name: {
              required,
              isFormat(name) {
                  return (/\D/.test(name));
              },
          },
          expiry: {
              required,
              isGoodFormat(expiry) {
                  return (
                      /^\d{2}\/\d{2}$/.test(expiry) &&
                      this.isCorrectMonth(expiry.substring(0, 2))
                      );
              },
          },
          cvv: {
              required,
              numeric,
              minLength: minLength(3),
              maxLength: maxLength(3),
          }
      }
  },
  props: {
  },
  methods: {
      submit() {
          this.errors = this.$v.ccForm.$anyError;
          console.log("this errors: " + this.errors);
          this.empty = !this.$v.ccForm.$anyDirty;
          if (this.errors === false && this.isTouched === false) {
              this.isSuccessfulSubmit = true;
              this.clearInputs();
          }
      },
      clearInputs() {
          this.ccForm.num = null;
          this.ccForm.name = null;
          this.ccForm.expiry = null;
          this.ccForm.cvv = null;
      },
      isCorrectMonth(substring) {
          var num = parseInt(substring);
          if (num >= 0 && num <= 12) {
              return true;
          }
          return false;
      },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>