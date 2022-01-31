<template>
    <main>
        <card-disc v-for="(disc, index) in discList"
        :key="index"
        :disc="disc" />
    </main>
</template>

<script>
import CardDisc from './CardDisc.vue'
export default {
    components: {
        CardDisc
    },
    props:{
        discList:Array
    }
    
}
</script>

<style lang="scss" scoped>

</style>