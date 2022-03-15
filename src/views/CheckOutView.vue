<template>
  <div class="wrapper">
    <div id="empty" v-if="cart.length === 0">
      <p>No Books to Checkout</p>
    </div>
    <div class="cart">
      <div class="item" v-for="item in cart" :key="item.id">
        
        <div class="image">
          <img :src="'/images/' + item.image" />
        </div>
        <div class="price">
          <button class="button" @click="removeFromCart(item); addBackBook(item);">Remove</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CartView",
  computed: {
    cart() {
      return this.$root.$data.cart;
    },
  },
  methods: {
    removeFromCart(item) {
      this.$root.$data.cart.splice(this.$root.$data.cart.indexOf(item), 1);
    },
    addBackBook(item){
      this.$root.$data.products.push(item);
    }
  },
};
</script>

<style scoped>
#empty {
  text-align: center;
  font-size: 50px;
}
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}
button {
      height: 50px;
      background: #000;
      color: white;
      border: none;
      width: 100%;
    }
.cart {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
.item {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}
.image img {
  border: 2px solid #333;
  height: 300px;
  width: 200px;
  object-fit: cover;
}
.item .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

</style>