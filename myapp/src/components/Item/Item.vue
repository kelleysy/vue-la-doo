<template>
  <li>
    <item-checkbox  :checked="checked"
                    @updateChecked="updateChecked">
    </item-checkbox>
    <item-label :labelText="labelText"
                @updateItemLabelText="updateLabelText">
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

  props: ['labelText', 'checked'],

  data () {
    return {
      label: '',
      isChecked: Boolean
    }
  },

  methods: {
    removeThisItem: function () {
      console.log('Item: removing')
      this.$emit('removeThisItem', this)
    },
    updateLabelText: function (newText) {
      this.label = newText
    },
    updateChecked: function (isChecked) {
      this.isChecked = isChecked
    }
  },

  created: function () {
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
