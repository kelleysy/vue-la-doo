<template>
  <span>
    <input type="text"  :value="labelText"
                        @input="updateItemLabelText"/>
  </span>
</template>

<script>
export default {

  name: 'item-label',

  props: ['labelText'],

  methods: {
    updateItemLabelText: function () {
      this.$emit('updateItemLabelText', this, this.labelText)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
