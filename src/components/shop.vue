<template>
<div class="give">
    <header>
        <button @click="navigateTo('products')">View products</button>
        <h2>{{cart.length}} in cart</h2>
        <button @click="navigateTo('cart')">View Cart</button>
    </header>
</div>

<div v-if="page ==='cart'">
    <div class="card" v-for="product in cart" :key="product.name">
        <div class="card-body row-3">
            <h3 class="card-title">{{product.name}}</h3>
            <p class="card-text">{{product.price}}</p>
            <p class="card-text"><img :src="product.image" alt=""> </p>
            <div class="btn btn-light" @click="removeItem(product)">Remove Item</div>

        </div>
    </div>
    <button class="btn btn-warning" type="submit">checkout</button>
</div>

<div v-if="page ==='products'">
    <div class="card" v-for="product in products" :key="product.name">
        <div class="card-body row-3">
            <h3 class="card-title">{{product.name}}</h3>
            <p class="card-text">{{product.price}}</p>
            <p class="card-text"><img :src="product.image" alt=""> </p>
            <a href="#" class="btn btn-primary" @click="addToCart(product)">Add to Cart</a>
        </div>
    </div>
</div>
</template>

<script>
export default {
    data() {
        return {

            page: "products",
            cart: [],
            products: [{
                    name: 'carrots',
                    price: '$4',
                    image: 'https://i.ndtvimg.com/mt/cooks/2014-11/carrots.jpg'
                },
                {
                    name: 'onions',
                    price: '$2',
                    image: 'https://4.imimg.com/data4/CW/MF/MY-35654338/fresh-red-onions-500x500.jpg'
                },
                {
                    name: 'cabbages',
                    price: '$2.3',
                    image: 'https://www.gardeningknowhow.com/wp-content/uploads/2019/12/cabbages.jpg'
                },
                {
                    name: 'bananas',
                    price: '$3.4',
                    image: 'https://cdn1.sph.harvard.edu/wp-content/uploads/sites/30/2018/08/bananas-1354785_1920-1200x800.jpg'
                },
                {
                    name: 'grapes',
                    price: '$5',
                    image: 'https://www.collinsdictionary.com/images/full/grape_229112122.jpg'
                }
            ]
        }
    },
    methods: {
        addToCart(product) {
            //console.log(product);
            this.cart.push(product);
            console.log(this.cart);

        },
        navigateTo(page) {
            this.page = page
        },
        removeItem(product) {
            this.cart.splice(this.cart.indexOf(product))
        }

    }

}
</script>

<style>
img {
    width: 300px;
}

.give {
    display: inline;
    background-color: grey;
    width: 300px;
}
</style>
