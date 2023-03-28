<script>
export default {
    name: 'Card',
    props: {
        img: String,
        title: String,
        type: String
    }
}
</script>

<template>
    <div class="card rounded-0 border-0 text-center" style="width: 18rem;">
        <img :src="img" class="card-img-top" :alt="name">
        <div class="card-body">
            <h6 class="card-title">{{ name }}</h6>
            <span>{{ type }}</span>
        </div>
    </div>
</template>

<style lang="scss">
@use '../assets/_partials/variables' as *;

.card {
    background-color: $primary;
}

</style>