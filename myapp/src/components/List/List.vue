<template>
  <div class="container">
    <h1>{{ title }}</h1>
    <ul>
      <li v-if="items.length === 0">No items!</li>
      <item v-for="item in items"
              :labelText="item.text"
              :checked="item.checked"
              @removeThisItem="removeItem"></item>
    </ul>
  </div>
</template>

<script>
import Item from '@/components/Item/Item'

export default {

  name: 'list',

  props: ['items'],

  components: {
    Item
  },

  data () {
    return {
      title: 'To Do List'
    }
  },

  methods: {
    removeItem: function (itemToDelete) {
      console.log('List: deleting')
      this.$emit('removeItem', itemToDelete)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  ul{
    list-style-type: none;
  }
</style>
