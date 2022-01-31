<template>
  <div id="app">
    
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'App',
  components: {

  },
  data(){
    return{
      discList:[]
    }
  },
  mounted(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((list) =>{
      this.discList=list.data.response;
      console.log(list)
    })
  }
}
</script>

<style lang="scss">

</style>
