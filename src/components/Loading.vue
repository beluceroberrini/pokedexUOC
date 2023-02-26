<template>
    <div class="loading">

        <figure class="image is-64x64">
            <img src=" https://www.freeiconspng.com/thumbs/pokeball-png/pokemon-ball-png-1.png">
        </figure>
        Loading
    </div>
</template>
<script setup>
</script>
<style scoped>
img {
    animation: loading-spin infinite 1s linear;
}

.loading {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    font-size: 2rem;
    height: 100%;
}

@keyframes loading-spin {
    0% {
        transform: rotate(0deg);
    }

    100% {
        transform: rotate(360deg);
    }

}
</style>