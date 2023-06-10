<template>
<h2>{{ name }}</h2>
<p>{{ user2.name }}</p>
<button v-on:click="getCheck()">Checked</button>
</template>

<script>
export default {
    name: "Child",
    props:{
        name:String,
         user2:Object,
         getCheck:Function
    }
}
console.log("hello")
</script>
