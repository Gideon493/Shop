<template>
<h1>cart</h1>

<div v-if="page ==='cart'">
    <div class="card" v-for="product in cart" :key="product.name">
        <div class="card-body row-3">
            <h3 class="card-title">{{product.name}}</h3>
            <p class="card-text">{{product.price}}</p>
            <p class="card-text"><img :src="product.image" alt=""> </p>
            <a href="#" class="btn btn-primary" @click="removeItem(product)">Remove Item</a>
        </div>
    </div>
</div>
</template>

<script>
export default {
    props:{
        products
    },
    data() {
        return {
            page: "products",
            cart: []
        }
    },
    methods: {
        removeItem(product) {
            this.cart.splice(this.cart.indexOf(product))
        }
    }

}
</script>

<style>

</style>
