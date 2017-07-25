<template>
  <input type="checkbox"  :checked="checked"
                          v-model="isChecked"
                          @click="updateChecked"/>
</template>

<script>
export default {

  name: 'item-checkbox',

  props: ['checked'],

  data () {
    return {
      isChecked: Boolean
    }
  },

  methods: {
    updateChecked: function () {
      this.$emit('updateChecked', this.isChecked)
    }
  },

  created: function () {
    this.isChecked = this.$props.checked
    this.updateChecked()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
