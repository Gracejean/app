<template>
  <div >
    <p>{{ sayings }}</p>
    <button 
    v-on:click="reverseMessage">Reversed</button>
    <br>
    <input v-model="type" type="text" />
    <br>
    <p>{{type}}</p>
    <span v-bind:title="title"> The visiting hours is over</span>
    <br>
    <br>
    <span v-if="seen">Now you see me</span>
    <ol>
        <li v-for="todo in todos" :key="todo.id">
            {{todo.text}}
        </li>
    </ol>
    <br>

  </div>
</template>

<script>
import Vue from 'vue';
    var data = {a:2}
    var obj = {
        foo:'bar'
    }
    Object.freeze(obj)
   var vm = new Vue({
       data: {
           obj: '',
           b: 8
       },
       created (){
           console.log('b is ' + this.b);
       }
       
       
   })
   console.log(vm.a == data.a);
   console.log(vm.a = 3);
   console.log(data.a);
   console.log(obj.foo)

export default {
  name: "Sayings",
  data() {
    return {
      sayings: "Never give up",
      type: null,
      title: 'The date today is ' + new Date().toLocaleString(),
      seen:false,
      todos:[
          {text: 'Study first'},
          {text: 'Practice more'},
          {text: 'Persevere'}
      ]
    };
  },
  methods: {
    reverseMessage() {
      this.sayings = this.sayings.split("").reverse("").join("");

    },
  },
};
</script>

<style scoped>
</style>