<template>
  <div class="container">
    <h1>{{ title }}</h1>
    <ul>
      <item v-for="item in items"
            v-bind:labelText="item.text"></item>
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
        {text: 'Take out the garbage'},
        {text: 'Feed the doggo'},
        {text: 'Pester the neigbor'},
        {text: 'Kung fu practice'}
      ]
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
