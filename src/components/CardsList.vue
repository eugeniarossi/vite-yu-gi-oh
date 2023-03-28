<script>
import axios from 'axios';
import CardElement from './CardElement.vue';

import { store } from '../store';

export default {
    name: 'CardsList',
    components: {
        CardElement
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class="container p-0">
        <div class="row cols-5 g-3" v-if="store.cardsFound !== 0">
            <div class="col-12 col-sm-3" v-for="card in store.cards.slice(0, 50)">
                <CardElement :img="card.card_images[0].image_url" :name="card.name.toUpperCase()"
                    :archetype="card.archetype" />
            </div>
        </div>
        <div v-else class="d-flex justify-content-center pt-5">
            <h5>Cards loading</h5>
        </div>
    </div>
</template>

<style scoped lang="scss"></style>