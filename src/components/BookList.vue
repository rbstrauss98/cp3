<template>
<div class="wrapper">
  <div class="products">
    <div class="product" v-for="product in products" :key="product.id">
      <div class="image">
        <img :src="'/images/'+product.image">
      </div>
      <div class="price">
        <button @click="addToCart(product); removeFromProduct(product);" class="auto">Check Out</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>
    export default {
      name: 'BookList',
      props: {
        products: Array
      },
      methods: {
        addToCart(product) {
          this.$root.$data.cart.push(product);
        },
        removeFromProduct(product){
          this.$root.$data.products.splice(this.$root.$data.products.indexOf(product), 1);
        }
      }
    };
</script>

<style scoped>
    .wrapper {
      display: flex;
      align-items: center;
      justify-content: center;
    }
    
    .products {
      margin-top: 20px;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-around;
    }
    
    .product {
      margin: 10px;
      margin-top: 50px;
      width: 200px;
    }
    
    .product img {
      border: 2px solid #333;
      height: 300px;
      width: 200px;
      object-fit: cover;
    }
    
    .product .image {
      display: flex;
      justify-content: center;
      margin-bottom: 5px;
    }
    .price {
      display: flex;
    }
    
    button {
      height: 50px;
      background: #000;
      color: white;
      border: none;
      width: 100%;
    }
    
    .auto {
      margin-left: auto;
    }
    </style>cs