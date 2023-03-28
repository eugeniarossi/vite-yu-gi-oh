<script>
export default {
    name: 'Card',
    props: {
        img: String,
        name: String,
        archetype: String
    }
}
</script>

<template>
    <div class="card rounded-0 border-0 text-center" style="width: 18rem;">
        <img :src="img" class="card-img-top" alt="">
        <div class="card-body">
            <h6 class="card-title text-white">{{ name }}</h6>
            <span>{{ archetype }}</span>
        </div>
    </div>
</template>

<style lang="scss">
@use '../assets/_partials/variables' as *;

.card {
    background-color: $primary;
    height: 100%;
}

</style>