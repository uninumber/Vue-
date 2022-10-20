<template>
<div>
<h3>{{task.text}}
<i @click="onDelete(task.id)" class="fas fa-times"></i>
</h3>
<p>{{task.day}}</p>
</div>
</template>

<script>
export default {
name: 'TheTask',
props: {
task: Object,
},
methods: {
onDelete(id) {
this.$emit('delete-task',id)
},
},
}
</script>
<style>
h3 {
margin-top:10px;
}
i {
float:right;
margin-right:10px;
margin-top:20px;
}
</style>
