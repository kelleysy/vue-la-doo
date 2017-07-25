<template>
  <div class="container">
    <h1>{{ title }}</h1>
    <ul>
      <li v-if="items.length === 0">No items!</li>
      <item v-for="(item, index) in items"
              :item.sync="item"
              :key="index"
              @removeThisItem="removeItem">
      </item>
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
      console.log('App; removing ')
      console.log(itemToDelete)
      this.items.splice(this.items.indexOf(itemToDelete), 1)
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
