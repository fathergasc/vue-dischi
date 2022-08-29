<template>
    <main>
        <LoadInProgress v-if="loadInProgress"/>
        <div class="container d-flex justify-content-center align-items-center">
            <div class="row row-cols-5 g-5 d-flex">
                <SingleAlbum v-for="(album, index) in albumList" :key="index" :album="album"/>
            </div>
        </div>
    </main>
  
</template>

<script>
import axios from 'axios';
import SingleAlbum from './SingleAlbum.vue';
import LoadInProgress from './LoadInProgress.vue';

export default {
    name: 'AlbumList',
    components: {
        SingleAlbum,
        LoadInProgress,
    },
    data() {
    return {
        albumList: [],
        genresList: [],
        endpoint: 'https://flynn.boolean.careers/exercises/api/array/music',
        loadInProgress: true,
    };
    },
    methods: {      
        getAlbums() {
            let that = this;
            axios
            .get(this.endpoint)
            .then((response) => {
                that.albumList = response.data.response;
                that.loadInProgress = false;
                console.log('that.albumList: ', that.albumList);
                that.createGenresList();
                that.$emit('genresList', that.genresList);
            
            })
            .catch((error) => {
                console.log(error);
                that.loadInProgress = false;
            });
        },
        createGenresList() {
            let that = this;
            this.albumList.forEach((album) => {
                if (!that.genresList.includes(album.genre)) {
                    that.genresList.push(album.genre);
                }
            })
            console.log('that.genresList: ', that.genresList);
            
        }
    },
    created() {
        this.getAlbums();
    }
};

</script>

<style lang="scss">
@import '@/styles/general.scss';

.row {
    img {
        width: 130px;
        height: 130px;
    }

    .album {
        padding: 15px;
        background-color: #2e3a46;
        height: 330px;

        &:hover {
            cursor: pointer;
            transform: scale(1.1);
        }

    }
}

.container {
    padding: 30px;
}



</style>