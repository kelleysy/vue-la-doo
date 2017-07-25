<template>
  <div class="container">
    <h1>{{ title }}</h1>
    <ul>
      <item v-for="item in items"
            :uid="item.id"
            :labelText="item.text"
            @deleteThisItem="deleteItem"></item>
    </ul>
  </div>
</template>

<script>
import Item from '@/components/Item/Item'

export default {

  name: 'list',

  components: {
    Item
  },

  data () {
    return {
      title: 'To Do List',
      items: [
        {id: 0, text: 'Take out the garbage'},
        {id: 1, text: 'Feed the doggo'},
        {id: 2, text: 'Pester the neigbor'},
        {id: 3, text: 'Kung fu practice'}
      ]
    }
  },

  methods: {
    addNewItem: function () {

    },
    deleteItem: function (keyToDelete) {
      console.log('List: deleting')
      console.log('key var -')
      console.log(keyToDelete)
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
