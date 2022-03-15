<template>
  <div class="container">
      <div class="card-wrapper">
          <div v-for="(el, i) in arrayAlbums" :key="i"  class="card">
              <div class="image">
                  <figure>
                      <img :src="el.poster" alt="">
                  </figure>
              </div>
              <div class="album-name">
                  <h3>{{el.title}}</h3>
              </div>
              <div class="album-artist">
                  <p>{{el.author}}</p>
              </div>
              <div class="album-genre">
                  <p>{{el.genre}}</p>
              </div>
              <div class="album-year">
                  <p>{{el.year}}</p>
              </div>
          </div>
      </div>
  </div>
</template>

<script>

import axios from 'axios'

export default {
    name: 'MsAlbums',
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

</style>