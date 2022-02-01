<template>
    <header>
        <select v-model="genreSelected">
            <option v-for='(genre, index) in genres'
            :key='index'
            @click="debug()">
                {{genre}}
            </option>
        </select>
    </header>
</template>

<script>
export default {
    data(){
        return{
            genreSelected:""
        }
    },
    props:{
        genres: Array
    },
    methods:{
        debug(){
            console.log("funziona")
        }
    }
    
}
</script>

<style lang="scss" scoped>
    header{
        height: 100px;
        background-color: #2E3A46;
    }
</style>