<template>
  <div id="app">
    <main-box :discList="discList"/>
  </div>
</template>

<script>
import axios from 'axios'
import MainBox from './components/MainBox.vue'

export default {
  name: 'App',
  components: {
    MainBox

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
@import './style/main.scss'

</style>
