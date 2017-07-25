<template>
  <li>
    <h2>
      {{ item.text }}
    </h2>
    <item-checkbox  :checked="item.checked">
    </item-checkbox>
    <item-label
      :labelText="item.text"
      @updateItemLabelText="updateItemLabelText">
    </item-label>
    <item-control @removeItem="removeThisItem">
    </item-control>
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

  props: ['item'],

  methods: {
    removeThisItem: function () {
      console.log('Item: removing')
      this.$emit('removeThisItem', this.item)
    },
    updateItemLabelText: function (item, labelText) {
      this.$emit('updateItemLabelText', item, labelText)
    }
  },

  created: function () {
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
