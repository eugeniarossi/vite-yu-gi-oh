<script>
import CardsList from './CardsList.vue';

export default {
    name: 'Main',
    components: {
        CardsList
    }
}
</script>

<template>
    <main>
        <div class="container pt-1 pb-3">
            <select class="form-select m-3"> // https://db.ygoprodeck.com/api/v7/archetypes.php
                <option selected>Alien</option>
                <option value="1">One</option>
                <option value="2">Two</option>
                <option value="3">Three</option>
            </select>
            <div id="cards" class="bg-white p-5">
                <div id="cards-found">
                    <h6 class="text-white p-3 fw-bold">Found 39 cards</h6>
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
    }
}
</style>