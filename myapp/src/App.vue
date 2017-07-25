<template>
  <div id="app">
    <add-item @addNewItem="addNewItem"></add-item>
    <list :items="items"
          @removeItem="removeItem"></list>
  </div>
</template>

<script>
import List from '@/components/List/List'
import AddItem from '@/components/List/Add_Item'

export default {
  name: 'app',

  components: {
    List,
    AddItem
  },

  data () {
    return {
      title: 'To Do List',
      items: [{
        text: 'Do the thing',
        checked: true
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
      console.log('App: deleting')
      console.log('item var -')
      console.log(itemToDelete)
      let indexOfDelete = this.items.indexOf(itemToDelete)
      console.log('index - ' + indexOfDelete)
      this.items.splice(indexOfDelete, 1)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
