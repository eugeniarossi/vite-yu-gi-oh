<script>
import axios from 'axios';
import CardElement from './CardElement.vue';

export default {
    name: 'CardsList',
    components: {
        CardElement
    },
    data() {
        return {
            cardsData: []
        }
    },
    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
        .then((response) => {
            console.log(response);
            this.cardsData = response.data.data;
            console.log(this.cardsData)
        })
    }
}
</script>

<template>
    <div class="container p-0">
        <div class="row g-3">
            <div class="col-12 col-sm-3" v-for="card in cardsData.slice(0,50)">
                <CardElement :img="card.card_images[0].image_url"
                :title="card.name"
                :type="card.archetype"/>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
</style>