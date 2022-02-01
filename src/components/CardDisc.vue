<template>
    <div class="disc-card py-3 px-2 mb-4 mx-2">
        <div class="img-box mb-2">
            <img class="img-fluid" :src="disc.poster" alt="">
        </div>
        <h5>{{disc.title.toUpperCase()}}</h5>
        <div class="txt-disc">{{disc.author}}</div>
        <div class="txt-disc">{{disc.year}}</div>
    </div>
</template>

<script>
export default {
    props:{
        disc:Object
    }
    
}
</script>

<style lang="scss" scoped>
    .disc-card{
        width: 200px;
        height: 300px;
        background-color: #2E3A46;
        .img-box{
            width: 150px;
            height: 150px;
            margin: 0 auto;

            img{
                width: 100%;
                object-fit: cover;
            }
        }

        h5{
            color: white;
            
        }

        .txt-disc{
            color:#6E6863;
        }


    }

</style>