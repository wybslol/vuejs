<template>
<div id="modal" class="w3-modal">
    <div class="w3-modal-content w3-card-4 w3-animate-zoom" style="max-width:600px">

      <div class="w3-center"><br>
        <span onclick="document.getElementById('modal').style.display='none'" class="w3-button w3-xlarge w3-hover-red w3-display-topright" title="Close Modal">&times;</span>
        <h3>Logo</h3>
      </div>

      <form @submit="onSubmit" class="w3-container">
        <div class="w3-section">
          <label><b>Task</b></label>
          <input class="w3-input w3-border w3-margin-bottom" v-model="text" type="text" name="title" required>
          <label><b>Assignment</b></label>
          <input class="w3-input w3-border w3-margin-bottom" v-model="intask" type="text"  name="intask" required>
        </div>
        <input onclick="document.getElementById('modal').style.display='none'" type="submit" class="w3-button w3-block w3-section w3-blue w3-ripple w3-padding">
      </form>

    </div>
  </div>
</template>

<script>
export default {
    name:'AddTask',
    data(){
        return{
           
            text:'',
            intask:'',
            active:true,
        }
    },emits: ['active-change', 'delete-task'],
    methods: {
        onSubmit(e){
            e.preventDefault() 

            const newTask= {
                id: Math.floor(Math.random()*10000),
                text: this.text,
                intask: this.intask,
                active: this.active
            }
            this.$emit('add-task', newTask)
            this.text =''
            this.intask=''
            this.active=true
        }
    }

}
</script>