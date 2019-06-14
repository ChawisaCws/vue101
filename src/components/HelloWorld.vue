<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{dataMessage}}</h1>
    <input v-model="dataMessage"/>
   

    <input type="number" v-model.number="a"/>
    <input type="number" v-model.number="b"/>
    <span>{{ printSum()}}</span>
    <br>
    <span>{{total}}</span>
    <br>
    <span>DataParent : {{ dataParent }}</span>
    <br>
    <child v-model="dataParent" />   
  </div>
</template>

<script>
import Child from './child.vue';
export default {
components:{
  Child
},
data(){
   return{ 
     dataMessage : 'Hello 55555',
     a : 10,
     b : 20,
     dataParent: 'jaaa'
   }
 },
 computed:{
   total(){
     return this.a+this.b;
     
   }
 },
 methods:{
   printSum(){
     return this.a+this.b;
     
   }
 },

 props:{
   msg: String
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
