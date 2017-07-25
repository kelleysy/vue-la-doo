<template>
  <button @click="remove"> - </button>
</template>

<script>
export default {

  name: 'item-control',

  methods: {
    remove: function (event) {
      this.$emit('removeItem')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
