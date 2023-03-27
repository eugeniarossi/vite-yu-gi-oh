<script>
export default {
    name: 'Card'
}
</script>

<template>
    <div class="card rounded-0 border-0 text-center" style="width: 18rem;">
        <img src="..." class="card-img-top" alt="...">
        <div class="card-body">
            <h6 class="card-title">Card title</h6>
            <span>alien</span>
        </div>
    </div>
</template>

<style lang="scss">
@use '../assets/_partials/variables' as *;

.card {
    background-color: $primary;
}

</style>