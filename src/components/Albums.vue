<template>
    <div class="card">
        <figure>
            <img :src="albumItems.poster" alt="">
        </figure>
        <h3>{{albumItems.title}}</h3>
        <p>{{albumItems.author}}</p>
        <p>{{albumItems.genre}}</p>
        <p>{{albumItems.year}}</p>
    </div>
</template>

<script>
export default {
    name: 'MsAlbums',
    props: {
        albumItems: {
            type: Object,
            required: true
        }
    }
}
</script>

<style scoped lang="scss">

.card {
    width: calc(100% / 5);
    padding: 30px;
    text-align: center;
}

img {
    max-width: 100%;
}

h3 {
    margin-top: 10px;
    font-weight: bold;
    color: white;
}

p {
    margin-top: 8px;
    color: grey;
}

</style>