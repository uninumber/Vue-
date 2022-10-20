<template>
<form @submit="onSubmit">
<div class="container5">
<div class="container4">
<label>Task: </label>
<input 
v-model="text"
style="float:right;margin-right:10px;"
type="text"
name="text"
placeholder="Add Tasks..." />
</div>
<br>
<div class="container4">
<label>Day: </label>
<input 
v-model="day"
style=" color:#000000;float:right;margin-right:10px;"
type="text"
name="day"
placeholder="Add Day..." />
</div>
</div>
<input 
type="submit" value="Save Task"
class="btn btn-block" />
</form>
</template>

<script>
export default {
name: 'AddTask',
data() {
return {
text: '',
day: ''
}
},
methods: {
onSubmit(e) {
e.preventDefault() 
if(!this.text){
alert("please add a task")
return
}
const newTask = {
id: Math.floor(Math.random() * 100000),
text: this.text,
day: this.day,
}
this.$emit('add-task', newTask)
this.text = ''
this.day = ''
}
}
}
</script>

<style>
input, select, textarea {
width: 200px;
border:2px solid black;
border-color:#000000;
text-align:center;
border-radius:10px;
}
input:focus, textarea:focus {
}
input:hover{
}
.container4 {
width: 300px;
text-align:center;
height: 30px;
}
.container5 {
width:300px;
height: 100px;
margin:1rem auto;
margin-left:120px;
}
label {
margin-left: 30px;
}
</style>


