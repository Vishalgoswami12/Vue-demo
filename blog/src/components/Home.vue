<template>
<h2>Hello Vishal Goswami</h2>
<p>Email-{{ email }}</p>
<h2>Mobile-{{ mobile }}</h2>
<h3>Name - {{ getName("vishal G") }}</h3>
<h4>Data - {{ getData().email }}</h4>
<button v-on:click="test()">Click Me</button>
<input type="text" v-model="count" />
<h3>{{ count }}</h3>
<br />
<input type="text" v-model="value" />
<button v-on:click="getInputData()">Value</button>

<h3>Technology</h3>
<label for="vue">Vue</label>
<input type="checkbox" value="Vue" id="vue" v-model="technology" />
<label for="react">React</label>
<input type="checkbox" value="react" id="react" v-model="technology" />
<br/>

<labe for="student">Student</labe>
<input type="radio" value="student" id="student" v-model="who" />

<labe for="developer">Developer</labe>
<input type="radio" value="developer" id="developer" v-model="who" />
<h4>Selected Technology {{ technology }}</h4>
<h4>I am - {{ who }}</h4>

<!-- if and else,toggle -->
<h5 v-if="show">Show If</h5>
<h5 v-else>Else</h5>
<button v-on:click="show=!show">Toggle</button>

<!-- for loop in vue -->
<ul>
    <li v-for="item in language" :key="item" >{{ item }}</li>
</ul>
<br/>
<br/>

<!-- loop on array of object -->
<ul>
    <li v-for="item in users" :key="item.id">Name-{{ item.user }} and age is {{ item.age }}</li>
</ul>

<!-- how to use child componet in parent componet -->
<Child name="Hello honey" :user2="user2" :getCheck="getCheck" />

</template>

<script>

import Child from "./Child.vue"

export default {
    name: "Home",
    components:{
        Child,
    },

    
    data() {
        return {
            email: "vishalgoswami2250@gmail.co",
            mobile: 9616664860,
            count: 0,
            value: null,
            technology: [],
            who:null,
            show:true,
            language:["java","php","js"],
            users:[
                {
                    user:"vishal",
                    age:"28",
                    id:1
                },
                {
                    user:"anish",
                    age:"20",
                    id:2
                },
                {
                    
                    user:"avsk",
                    age:"26",
                    id:3
                
                }
            ],
            user2:{
                name:"rajesh",
                age:9,
            },
            check:"Hii Anish"
        }
    },
    methods: {
        getName(name) {
            return name;
        },
        getData() {
            return {
                name: "Akash",
                last: "chaudhary",
                email: this.email
            }
        },
        test() {
            this.count = this.count + 1
        },
        getInputData() {
            console.log(this.value)
        },
        getCheck(){
            alert(this.check)
        }
    }
}
</script>

<style scoped>
h2 {
    color: blue;
}
</style>
