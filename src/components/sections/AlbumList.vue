<template>
    <div class="container">
        <SearchBar @search="searchGenre" @reset="resetAlbum"/>

        <!-- v-if per il loader -->
        <div v-if="title != null" class="row">
        
        <div class="row row-cols-2 row-cols-md-3 row-cols-lg-5">
            <div class="col" v-for="(titles, index) in genreFilter" :key="index">
                <AlbumCard :info="titles"/>
            </div>
        </div>

        </div>
        <!-- v-else loader -->
        <div v-else class="loader">
            <h1>LOADING...</h1>
        </div>
    </div>
</template>

<script>
import AlbumCard from '../commons/AlbumCard.vue';
import axios from 'axios';
import SearchBar from '../commons/SearchBar.vue';

export default {
    
    name: 'AlbumList',
    components:{
        AlbumCard,
        SearchBar,
    },
    data () {
        return{
            title: null,
            loader: false,
            genreFilter: null,
        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            // handle success
            this.title = response.data.response;
            // this.GenreFiltered = response.data.response;
        })
        .catch(function (error) {
            // handle error
            console.log(error);
        });
    },
    methods:{
        searchGenre(payload){
            this.filterValue = payload;
        },
        reset(){
            this.filterValue = "";
        },
    },

    computed:{
        genreFiltered(){
                return this.albums.filter((elm) => {
                if(elm.titles.toLowerCase().includes(this.filterValue.toLowerCase())) {
                    return elm;
                }

                else if(elm.genre == this.filterValue){
                    return elm;
                }
                
                else if(elm.author == this.filterValue){
                    return elm;
                }
                // true or false
                // if il genere è true mantengo la card, altrimenti la scarto
            });
        }
    }
}
</script>

<style lang="scss" scoped>
    .container{
        max-width: 1100px;
        margin-top: 50px;
    }
    .loader{
        color: yellow;
        text-align: center;
    }
</style>