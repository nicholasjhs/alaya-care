<template>
    <nav class="checkout-nav">
        <ul class="nav-links">
            <li class="nav-item" v-for="(link, index) in links" v-bind:key="index">
                <a :class="link.active ? 'active': ''" href="#">{{ link.name }}</a>
            </li>
        </ul>
    </nav>
</template>

<script>

export default {
  name: 'Nav',
  components: {
  },
  data() {
      return {
      }
  },
  props: {
      links: {
          type: Array,
          required: true,
          default: ''
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>