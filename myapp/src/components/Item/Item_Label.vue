<template>
  <span>
    <input type="text" ref="labelText"
      :value="this.labelText"
      @input="updateItemLabelText"/>
  </span>
</template>

<script>
import { EventBus } from '@/event-bus.js'

export default {

  name: 'item-label',

  props: ['labelText'],

  methods: {
    updateItemLabelText: function () {
      console.log('emitting from label')
      EventBus.$emit('updateItem', this.$parent, this.$refs.labelText.value)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
