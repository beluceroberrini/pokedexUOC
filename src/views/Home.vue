<template>
    <div class="welcome">
        <h1 class="title">Bienvenido al mundo Pokemon</h1>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. In, laudantium eaque mollitia dolore numquam sed? Rem optio quaerat adipisci error.</p>
        <h2 class="title">GO!</h2>
    </div>
</template>
<script setup>
</script>
<style scoped>

.welcome{
    display: flex;
    justify-content:center;
    flex-direction: column; 
    align-items: center;
    padding-top: 120px;
}
.title {
    margin: 20px;
    font-size: 50px;
}

h2{
    margin: 50px;
    font-size: 50px;
}
p{
    width: 45%;
}
</style>