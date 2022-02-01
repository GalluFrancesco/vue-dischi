<template>
  <div id="app">
    <header-box @selected="filterResult" :genres="genreList"/>
    <main-box :discList="discFiltered"/>
  </div>
</template>

<script>
import axios from 'axios'
import MainBox from './components/MainBox.vue'
import HeaderBox from './components/HeaderBox.vue'

export default {
  name: 'App',
  components: {
    HeaderBox,
    MainBox

  },
  data(){
    return{
      discList:[],
      discFiltered:[],
      genreList:['All'],
      timer: 0
    }
  },
  methods:{
    fillGenreList(){
        this.discList.forEach(disc => {
          if(!this.genreList.includes(disc.genre)){
            this.genreList.push(disc.genre)
          }
        });
    },
    filterResult(word){
        console.log('debug')
        this.discFiltered= this.discList.filter((disc) =>{
          return disc.genre===word || word==='All';
        })
    },
  },
  mounted(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((list) =>{
      this.timer=setTimeout(() => {
        this.discList=list.data.response;
        this.discFiltered=this.discList;
        this.fillGenreList();   
      }, 2000)
    })
  }
}
</script>

<style lang="scss">
@import './style/main.scss'

</style>
