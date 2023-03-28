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
        <div class="row cols-5 g-3">
            <div class="col-12 col-sm-3" v-for="card in store.cards.slice(0,50)">
                <CardElement :img="card.card_images[0].image_url" :name="card.name.toUpperCase()" :archetype="card.archetype"/>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
</style>