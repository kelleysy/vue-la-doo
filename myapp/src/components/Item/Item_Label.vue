<template>
  <span>
    <input type="text"  :value="labelText"
                        v-model="label"
                        @input="updateItemLabelText"/>
  </span>
</template>

<script>
export default {

  name: 'item-label',

  props: ['labelText'],

  data () {
    return {
      label: ''
    }
  },

  methods: {
    updateItemLabelText: function () {
      this.$emit('updateItemLabelText', this.label)
    }
  },

  created: function () {
    // console.log(this)
    this.label = this.$props.labelText
    this.updateItemLabelText()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
