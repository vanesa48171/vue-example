<template>
  <div id="app">
    <NavBarPrueba />
    <input type=text v-model='actual.name'/>
    <input type=text v-model='actual.lastname'/>
    <button @click="uploadData()" >Cargar</button>
    <NavBar />
    <br/>

    <div v-for="(item,i) in list" :key="i"> 
      Name: {{item.name}}
      <br/>
      Lastname: {{item.lastname}}
    </div>
    <NavBar />
  </div>
</template>

<script>
import NavBarPrueba from './components/NavBar'
import HelloWorld from './components/HelloWorld'

export default {
  name: "App",
  components: {
    NavBarPrueba,
    
  },
  data(){return{
    list: [],
    actual: {
      name: '',
      lastname: ''
    }
  }},
  methods:{
    uploadData(){
      this.list.push(this.actual)
      this.actual = {
        name: '',
        lastname: ''
      }
    }
  }
};
</script>

<style>

</style>
