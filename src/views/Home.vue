<template>
    <div>
        <div class="homepage-grid">
            <div class="black-and-center" v-for="product in $root.$data.products" :key="product.id">
                <img :src="'../img/'+product.image">
                <img src="../img/ChurchWindow.jpg">
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Home",
        props: {
            products: Array
        },
    }
</script>

<style scoped>

</style>