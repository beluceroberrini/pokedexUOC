<template>
    <nav class="navbar" role="navigation" aria-label="main navigation">
        <div class="navbar-brand">
            <router-link class="navbar-item" :to="{Home}">
                <img
                    src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/98/International_Pok%C3%A9mon_logo.svg/2560px-International_Pok%C3%A9mon_logo.svg.png">
            </router-link> 

<!-- 
        <section class="moon">
            <img src="./imagenes/moon-solid.svg" id="icon" class='icon' alt="">
            <button class="myButton"></button>
        </section> -->
        </div>
    </nav>
</template>
<script setup>
import Home from '../views/Home.vue';

</script>
<style>
.navbar{
    background-color: white;
    box-shadow: 0 0 2rem -1rem rgba(0, 0, 0, 0.5);
    --color-bg: var(--clr-white);
    display: flex;
    height: 12vh;
    justify-content: center;
    align-items: center;
}

.navbar img{
    max-height: 3rem!important;
}

</style>