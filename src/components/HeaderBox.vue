<template>
    <header>
        <select v-model="genreSelected" @change="$emit('selected', genreSelected)">
            <option v-for='(genre, index) in genres'
            :key='index'>
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
    }    
}
</script>

<style lang="scss" scoped>
    header{
        height: 100px;
        line-height: 100px;
        background-color: #2E3A46;
        padding: 0 24px;

        select{
            width: 100px;
        }
    }
</style>