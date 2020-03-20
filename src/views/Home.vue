<template>
    <div>
        <div class="homepage-grid">
            <div class="black-and-center" v-for="product in $root.$data.products" :key="product.id">
                <div class="image">
                    <img :src="require('../img/' + product.image)">
                </div>
                <div class="price">
                    <h2>{{product.price}}</h2>
                    <button class="auto" @click="addToCart(product.id)">Add to Cart</button>
                </div>

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
        methods: {
            addToCart(id){
                for(let i=0; i < this.$root.$data.cart.length ;i++){
                    if(id === this.$root.$data.cart[i][0]){
                        let tmp = this.$root.$data.cart[i][2];
                        this.$root.$data.cart.splice(i, 1);
                        this.$root.$data.cart.push([id, this.$root.$data.products[id - 1], tmp + 1]);
                        return
                    }
                }
                this.$root.$data.cart.push([id, this.$root.$data.products[id - 1], 1]);
            }
        }
    }
</script>

<style scoped>

</style>