<template>
    <main>
        <div class="container">
            <div class="album-container">
                <Albums />
            </div>
        </div>
    </main>
</template>

<script>
import Albums from './Albums.vue'

export default {
    name: 'MsMain',
    components: {
        Albums,
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


</style>