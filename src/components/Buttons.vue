<template>
    <button @click="OnClick()" onclick="document.getElementById('modal').style.display='block'" class="w3-button w3-circle w3-black">{{text}}</button>
</template>

<script>
export default {
   name: 'Buttons',
   props: {
       text: String,
   },
   methods: {
       OnClick(){
           
       }
   }
}
</script>

<style>

</style>