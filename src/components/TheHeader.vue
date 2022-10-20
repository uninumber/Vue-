<template>

<header>

<h1> {{title}}</h1>
<TheButton @toggle-add-task="$emit('toggle-add-task')" :text="showAddTask? 'Close' : 'Append'"/>
</header>
</template>

<script>
import TheButton from './TheButton'
export default {
name: 'TheHeader',
props: {
title: String,
showAddTask: Boolean
},
components: {
TheButton
}
}
</script>

<style>
header {
display:flex;
justify-content:space-between;
align-items: center;
margin-bottom: 10px;
}
</style>

