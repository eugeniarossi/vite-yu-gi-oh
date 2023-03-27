<script>
import CardElement from './CardElement.vue';

export default {
    name: 'CardsList',
    components: {
        CardElement
    }
}
</script>

<template>
    <div class="container p-0">
        <div class="row g-3">
            <div class="col-12 col-sm-3">
                <CardElement></CardElement>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
</style>