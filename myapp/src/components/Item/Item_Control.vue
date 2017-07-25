<template>
  <button @click="deleteItem"> - </button>
</template>

<script>
export default {

  name: 'item-control',

  data () {
    return {
    }
  },

  methods: {
    deleteItem: function (event) {
      console.log('Item Control: deleting')
      console.log('event var - ')
      console.log(event)
      this.$emit('deleteItem')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
