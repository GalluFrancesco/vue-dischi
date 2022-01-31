<template>
    <main class="vh-100">
        <div class="d-flex flex-wrap justify-content-between container-disc pt-5">
            <card-disc v-for="(disc, index) in discList"
            :key="index"
            :disc="disc" />
        </div>
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
    main{
        background-color: #1E2D3B;

        .container-disc{
            width: 1100px;
            margin: 0 auto;
            text-align: center;
        }
    }

</style>