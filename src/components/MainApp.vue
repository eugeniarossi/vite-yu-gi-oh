<script>
import axios from 'axios';
import CardsList from './CardsList.vue';
import { store } from '../store';

export default {
    name: 'Main',
    components: {
        CardsList
    },
    data() {
        return {
            store,
            archetypes: []
        }
    },
    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
            .then((response) => {
                this.archetypes = response.data;
            })
    }
}
</script>

<template>
    <main>
        <div class="container pt-1 pb-3">
            <select class="form-select m-3" v-model="store.selectValue" @change="$emit('search')">
                <option selected></option>
                <option :value="archetype.archetype_name" v-for="archetype in archetypes">{{ archetype.archetype_name }}</option>
            </select>

            <div id="cards" class="bg-white p-5">
                <div id="cards-found">
                    <h6 class="text-white p-3 fw-bold">Found {{ store.cardsFound }} cards</h6>
                </div>
                <CardsList />
            </div>
        </div>
    </main>
</template>

<style scoped lang="scss">
@use '../assets/_partials/variables' as *;

main {
    background-color: $primary;

    select {
        width: 15rem;
    }

    #cards-found {
        background-color: $secondary;
        margin-bottom: -1.5rem;
    }
}
</style>