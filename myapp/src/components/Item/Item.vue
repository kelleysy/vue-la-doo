<template>
  <li>
    <item-checkbox></item-checkbox>
    <item-label v-bind:labelText="labelText"></item-label>
  </li>
</template>

<script>
import ItemCheckbox from '@/components/Item/Item_Checkbox'
import ItemLabel from '@/components/Item/Item_Label'

export default {

  name: 'item',

  components: {
    ItemCheckbox,
    ItemLabel
  },

  props: ['labelText'],

  data () {
    return {
      content: 'test',
      checked: false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
