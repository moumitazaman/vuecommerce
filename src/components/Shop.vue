<script setup>
import {ref,onBeforeMount} from 'vue'
import axios from 'axios'

const products = ref({})
onBeforeMount(() => {
   
    axios.get('https://dummyjson.com/products?limit=10')
        .then(res => {
            products.value = res.data.products
        })
})


</script>
<template>
    
    
    <div class="product-big-title-area">
        <div class="container">
            <div class="row">
                <div class="col-md-12">
                    <div class="product-bit-title text-center">
                        <h2>Shop</h2>
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    
    <div class="single-product-area">
        <div class="zigzag-bottom"></div>
        <div class="container">
            <div class="row">
                <template v-for="product in products" :key="product.id">
                <div class="col-md-3 col-sm-6">
                    <div class="single-shop-product">
                        <div class="product-upper">
                            <img :src="product.thumbnail" alt="">
                        </div>
                        <h2><router-link :to="{ name: 'details', params: { id: product.id } }">{{ product.title }}</router-link></h2>
                        <div class="product-carousel-price">
                            <ins>{{product.price}}</ins> 
                        </div>  
                        
                        <div class="product-option-shop">
                            <a class="add_to_cart_button" data-quantity="1" data-product_sku="" data-product_id="70" rel="nofollow" href="/canvas/shop/?add-to-cart=70">Add to cart</a>
                        </div>                       
                    </div>
                </div>
                </template>
             </div>
                <div class="row">
                    <div class="col-md-12">
                        <div class="product-pagination text-center">
                                                 
                        </div>
                    </div>
                </div>
            </div>
        </div>
    
    
      
   
    
</template>
<style></style>