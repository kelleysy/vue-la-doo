<template>
  <input type="checkbox"  v-model="checked"
                          @click="updateChecked"/>
</template>

<script>
export default {

  name: 'item-checkbox',

  data () {
    return {
      checked: false
    }
  },

  methods: {
    updateChecked: function () {
      this.$emit('updateChecked', this.checked)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
