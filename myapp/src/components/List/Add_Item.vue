<template>
  <div>
    <input type="text"  v-model="label"
                        @keyup.enter="addNewItem"/>
    <button @click="addNewItem">+</button>
  </div>
</template>

<script>
export default {

  name: 'add-item',

  data () {
    return {
      label: ''
    }
  },

  methods: {
    addNewItem: function () {
      if (this.label !== '') {
        this.$emit('addNewItem', {
          text: this.label,
          checked: false
        })
      }
      this.label = ''
    }
  },

  created: function () {
    // console.log(this)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
