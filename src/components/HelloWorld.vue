<template>
  <div class="hello" >
    <h1>{{ msg }}</h1>
    <br>
    <Sayings :color="color"/>
    <div id="greet">
    <user-name name="Jean"></user-name>

    </div>
  </div>
</template>

<script>
import Sayings from './Sayings'
//  import Vue from 'vue'
import Vue from 'vue/dist/vue.js';

    Vue.component('user-name',{
        props:['name'],
        template:
            `<p>Good morning {{name}}</p>`
    })

    window.onload = function(){
       new Vue({
      el:'#greet'
    })
    }
    


export default {
  
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data (){
    return{
      color: 'red'
    }
  },
  components: {
    Sayings,
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
