<template>
    <div class="titles text-center">
        <img class="mb-3" :src="info.poster" :alt="info.title">
        <h4>{{info.title}}</h4>
        <p>{{info.author}}</p>
        <p>{{info.year}}</p>
    </div>
</template>

<script>
export default {
    name: 'AlbumCard',
    props:{
        info: Object,
    }
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/global.scss';

    .titles{
        background-color: $softBlue;
        color: white;
        height: 340px;
        margin: 10px 0;
        padding: 20px;

        img{
            width: 100%;
            aspect-ratio: 1/1;
        }

        h4{
        text-transform: uppercase;
        }

        p{
            color: gray;
            margin: 0;
        }    
    }

</style>