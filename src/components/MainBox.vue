<template>
    <main class="vh-100 position-relative">
        <div v-if="discList.length===10">
            <div class="d-flex flex-wrap justify-content-between container-disc pt-5">
                <card-disc v-for="(disc, index) in discList"
                :key="index"
                :disc="disc" />
            </div>
        </div>
        <div v-if="discList.length<10">
            <main-loader />
        </div>
    </main>
</template>

<script>
import CardDisc from './CardDisc.vue'
import MainLoader from './MainLoader.vue'
export default {
    components: {
        CardDisc,
        MainLoader
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