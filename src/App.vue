<template>
<div class="container center">
<h4><TheHeader @toggle-add-task="toggleAddTask" title="Tasks Content" :showAddTask="showAddTask"/></h4>
<div v-show="showAddTask">
<AddTask @add-task="addTask"/>
</div>
<Tasks @delete-task="deleteTask" :tasks="tasks"/>
</div>
</template>

<script>
import TheHeader from './components/TheHeader'
import Tasks from './components/Tasks'
import AddTask from './components/AddTask'

export default {
  name: 'App',
  components: {
  TheHeader,
  Tasks,
  AddTask,
  },
  data() {
  return {
  tasks: [],
  showAddTask:false 
  }
  },
  methods: {
  toggleAddTask() {
  this.showAddTask = !this.showAddTask
  },

 async addTask(task) {
 this.tasks = [...this.tasks, task]
  },
  deleteTask(id) {
  this.tasks = this.tasks.filter((task) => task.id !== id)
  },
async fetchTasks() {
const res = await fetch('http://localhost:5000/tasks')
const data = await res.json()
return data
},
async fetchTask(id) {
const res = await fetch(`http://localhost:5000/tasks/${id}`)
const data = await res.json()
return data
},
},
async created() {
this.tasks = await this.fetchTasks()
},
}



</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000;
  margin-top: 60px;
}

.container {
margin: 1rem auto;
width:600px;
background:#2f4f4f;
border: 3px solid #52595D;
border-radius:5px;
text-align:center;
}
h4 {
margin-left:12rem;
}
</style>

