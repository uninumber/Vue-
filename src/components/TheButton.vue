<template>
<button @click="onClick()" class="btn">{{text}}</button>
</template>

<script>
export default {
name: 'TheButton',
props: {
text: String,
color: String,
},
methods: {
onClick() {
this.$emit('toggle-add-task')
},
},
}
</script>
<link rel="stylesheet" href="style.css">
<style>
.btn {
background-color:#242425;
color:#fff;
font-weight:bold;
border: 2px solid #242425;
border-radius: 5px;
margin:10px;
}
</style>
