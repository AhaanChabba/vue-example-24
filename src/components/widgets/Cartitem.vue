
<script>
export default {
    props: {
        productItem: {
            imageUrl: String,
            productname: String,
            productdiscription : String,
            productprice: String,
           
    },
}
}
</script>

<template>
    <div class="product-item">
        <a :href="product.imageUrl">
            <div class="product-item__image">
                <img :src="product.imageUrl" alt="product image" />
            </div>
            <div class="product-item__discription">
                <h3 class="product-item__title">{{ productItem.title }}</h3>
                <productItemFooter :article="productItem"></productItemFooter>
            </div>
        </a>
    </div>

<div>
<img :src="productItem.imageUrl" alt="product image" />
<h3>{{productItem.productName}}</h3>
<p>{{productItem.productDesc}}</p>
<p>{{productItem.productPrice}}</p>
<button @click="addCart">Add to Cart</button>
<p>{{ count }}</p>
<button @click="addAmt">+</button>
<button @click="subAmt">-</button>
</div>

</template>
