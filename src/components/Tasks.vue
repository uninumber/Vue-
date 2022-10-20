<template>
<div  v-bind:key="task.id" v-for="task in tasks" class="task">
<Task @delete-task="$emit('delete-task', task.id)" :task="task" />
</div>
</template>

<script>
import Task from './Task'
export default {
name: 'TheTasks',
props: {
tasks: Array
},
components: {
Task,
},
emits: ['delete-task'],
}
</script>
<style>
.task {
background: #f4f4f4;
width:400px;
height:80px;
margin:1rem auto;
cursor: pointer;
border-radius:5px;
margin-bottom:20px;
}
</style>
