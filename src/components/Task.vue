<template>
<div class="w3-row w3-grey w3-opacity-min w3-round-xlarge">
        <div class="w3-col w3-grey w3-container w3-round-xlarge" style="position:relative;top:30px;z-index:1;width:5.5%"><button @click="$emit('active-change', task.id)" :class="[task.active ? ' w3-button w3-hover-red w3-circle w3-green': 'w3-button w3-hover-green w3-circle w3-red  ', 'task']" style="height:30px;"></button></div>
        <div class="w3-col w3-grey w3-container" style="width:87%"><h3>{{task.text}}</h3><p>{{task.intask}}</p></div><br>
        <div class="w3-col w3-grey w3-container w3-round-xlarge" style="width:7.5%"><i @click ="$emit('delete-task',task.id)" class="fa fa-trash w3-xlarge w3-right" ></i></div>
    </div>  
    <br> 
</template>

<script>
export default {
    name:'Task',
    props:{
        task: Object,
    },
}
</script>