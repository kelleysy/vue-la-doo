<template>
  <span>
    <input type="text" :value="labelText"/>
  </span>
</template>

<script>
export default {

  name: 'item-label',

  props: ['labelText'],

  data () {
    return {
      label: 'Do this task!'
    }
  },

  created: function () {
    console.log(this)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
