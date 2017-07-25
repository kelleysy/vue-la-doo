<template>
  <div class="container">
    <h1>{{ title }}</h1>
    <add-item @addNewItem="addNewItem"></add-item>
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
import AddItem from '@/components/List/Add_Item'

export default {

  name: 'list',

  components: {
    Item,
    AddItem
  },

  data () {
    return {
      title: 'To Do List',
      items: [{
        text: 'Do the thing',
        checked: false
      }]
    }
  },

  methods: {
    addNewItem: function (newItem) {
      console.log('Adding - ')
      console.log(newItem)
      this.items.push(newItem)
    },
    removeItem: function (itemToDelete) {
      console.log('List: deleting')
      console.log('item var -')
      console.log(itemToDelete)
      let indexOfDelete = this.items.indexOf(itemToDelete)
      console.log('index - ' + indexOfDelete)
      this.items.splice(indexOfDelete, 1)
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
