<template>
  <li>
    <item-checkbox></item-checkbox>
    <item-label :labelText="labelText"
                @updateItemLabelText="updateLabelText"></item-label>
    <item-control @deleteItem="deleteThisItem"></item-control>
  </li>
</template>

<script>
import ItemCheckbox from '@/components/Item/Item_Checkbox'
import ItemControl from '@/components/Item/Item_Control'
import ItemLabel from '@/components/Item/Item_Label'

export default {

  name: 'item',

  components: {
    ItemCheckbox,
    ItemLabel,
    ItemControl
  },

  props: ['uid', 'labelText'],

  data () {
    return {
      id: 0,
      content: 'test',
      checked: false
    }
  },

  methods: {
    deleteThisItem: function () {
      console.log('Item: deleting')
      this.$emit('deleteThisItem', this.key)
    },
    checkInfo: function () {
      console.log('=============Log================')
      console.log('this / data / props')
      console.log(this)
      console.log(this.$data)
      console.log(this.$props)
    },
    updateLabelText: function (newText) {
      this.content = newText
    },
    updateChecked: function (isChecked) {
      this.checked = isChecked
    }
  },

  created: function () {
    // this.checkInfo()
    this.id = this.$props.uid
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
