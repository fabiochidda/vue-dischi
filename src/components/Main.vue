<template>
    <main>
        <div class="container">
            <div class="album-container">
                <Albums v-for="(el, i) in arrayAlbums" :key="i" :albumItems="el"/>
            </div>
        </div>
    </main>
</template>

<script>
import Albums from './Albums.vue'
import axios from 'axios'

export default {
    name: 'MsMain',
    components: {
        Albums,
    },
    data() {
        return {
            arrayAlbums: []
        }
    },
    methods: {
        albumsRequest: function() {

            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then( answ => {

                this.arrayAlbums = answ.data.response

            })

        }
    },
    created() {
        this.albumsRequest()
    }
}
</script>

<style scoped lang="scss">

.container {
    height: calc(100vh - 88px);
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #1E2D3B;
}

.album-container {
    max-width: 1320px;
    display: flex;
    flex-wrap: wrap;
}

</style>