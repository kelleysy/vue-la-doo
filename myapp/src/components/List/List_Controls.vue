<template>
  <div>
    <control-knob>Add</control-knob>
    <control-knob>Clear</control-knob>
  </div>
</template>

<script>
import ControlKnob from '@/components/List/Control_Knob'

export default {

  name: 'list-controls',

  components: {
    ControlKnob
  },

  data () {
    return {

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
