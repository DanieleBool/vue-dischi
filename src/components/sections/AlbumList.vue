<template>
    <div class="container">
        <div class="row row-cols-2 row-cols-md-3 row-cols-lg-5">
            <div class="col" v-for="(titles, index) in title" :key="index">
                <AlbumCard :info="titles"/>
            </div>
        </div>
    </div>
</template>

<script>
import AlbumCard from '../commons/AlbumCard.vue';
import axios from 'axios';

export default {
    
    name: 'AlbumList',
    components:{
        AlbumCard,
    },
    data () {
        return{
            title: null,
        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            // handle success
            this.title = response.data.response;
        })
        .catch(function (error) {
            // handle error
            console.log(error);
        });
    }
}
</script>

<style lang="scss" scoped>
    .container{
        max-width: 1100px;
        margin-top: 50px;
    }
</style>