<template>
  <div id="app">
    <CheckOut/>
  </div>
</template>

<script>
import CheckOut from './components/CheckOut.vue'

export default {
  name: 'app',
  components: {
    CheckOut,
  }
}
</script>

<style lang="scss">
@import "assets/css/main.scss";
</style>
