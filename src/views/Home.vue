<template>
    <section class="input-container">
        <input v-model="findPoke" class="input" type="text" placeholder="¿Que Pokemon deseas ver?">
    </section>
    <section v-if="!isLoading" class="section container">
        <div class="columns is-multiline is-centered is-mobile">
            <div v-for="(pokemon, index) in pokemons" :key="pokemon.name"
                class="column is-6-mobile is-4-tablet is-3-desktop is-2-widescreen ">
                <router-link :to="{name:'details', params:{id: index + 1}}">
                    <PokeCard :name="pokemon.name" :id="index + 1" />
                    
                </router-link>
            </div>
        </div>
    </section>
    <div class="loading-container" v-else>
        <Loading />
    </div>
</template>
<script setup>
import { onMounted, ref, computed} from 'vue';
import { getPokemons } from '../api';
import PokeCard from '../components/PokeCard.vue';
import Loading from '../components/Loading.vue';
const pokemons = ref([]);
const isLoading = ref(true);

const findPoke = ref('');

onMounted(async () => {
    console.log('montado')
    const res = await getPokemons();
    isLoading.value = false;
    pokemons.value = res.results;
})

const pokeFilter = computed(() =>{
    let filter = findPoke.value
    if(!filter.length) return pokemons.value
    return pokemons.value.filter(poke =>
    poke.name.toLowerCase().includes(filter.toLowerCase())
    )
})


</script>
<style scoped>
.loading-container{
    height: calc(100vh - 52px);
    display: flex;
    justify-content: center;
    align-items: center;
}

.input-container {
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
    padding: 15px;
}

.input {
    display: flex;
    font-size: 12px;
    width: 28%;
    border: none;
    border-radius: 14px;
    padding: 5px 10px;
    height: 25px;
    text-align: center;
}
</style>
