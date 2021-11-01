<template>
  <Tasks @active-change="activeChange" @delete-task="deleteTask" :tasks="tasks"/>
  <Tracker />
  <AddTask  @add-task="addTask"/>
</template>

<script>
import Tracker from './components/Tracker'
import Tasks from './components/Tasks.vue'
import AddTask from './components/AddTask.vue'

export default {
  name: 'App',
  components: {
    Tracker,
    Tasks,
    AddTask
  },
    methods: {
      deleteTask(id){
        this.tasks = this.tasks.filter((task)=> task.id !== id )
      }
,
      activeChange(id){
        this.tasks = this.tasks.map((task)=> task.id === id ? {...task, active:!task.active}: task)
      },
      addTask(task){
        this.tasks = [...this.tasks, task]
      }

  }
  ,
    data(){
      return{
        tasks: []
    }
  },
    created(){
      this.tasks = [
      {
        id:1,
        text:'Task 1',
        intask: 'John Wick',
        active:true
      },
      {
        id:2,
        text:'Task 2',
        intask: 'Another Jonh Wick',
        active:false
      },
      {
        id:13,
        text:'Task 3',
        intask: 'John Wick 3rd',
        active:true
      },
      ]
    }
}
</script>

<style>
</style>
