<template>
    <div class="w3-grey w3-opacity w3-round-xlarge w3-panel w3-padding-16">
      <div class="w3-row">
        <div class="w3-col" style="position:relative;top:12.5px;z-index:1;width:7.5%"><Buttons text="+"/></div>
        <div class="w3-col m8 l9" ><h3>Add task</h3></div>
      </div>
    </div>
</template>

<script>
import Buttons from './Buttons.vue'
export default {
  name: 'Tracker',
  components:{
    Buttons
  }
}
</script>

<style>

</style>