<template>
<div>
  <div class="wrapper">
    <div class="search">
      <form class="pure-form">
        <i class="fas fa-search"></i><input v-model="searchText" />
      </form>
    </div>
    <h3 style="align-self:center;">Genres</h3>
    <div class="genre-container">
      <button class="menu-item" @click="filter = ''">
        <p class="menu-text">All</p>
      </button>
      <button class="menu-item" @click="filter = 'Fiction'">
        <p class="menu-text">Fiction</p>
      </button>
      <button class="menu-item" @click="filter = 'Non-Fiction'">
        <p class="menu-text">NonFiction</p>
      </button>
    </div>
  </div>
  <BookList :products="products" />
  <div class="footer">
    <p class="footer-text">This is the link to my github repository for this lab: 
    <a href="https://github.com/rbstrauss98/cp3">repository</a>
    </p>   
  </div>
</div>

</template>

<script>
import BookList from "../components/BookList.vue"
export default {
  name: 'HomeView',
  components: {
    BookList
  },
  data() {
    return {
      filter: '',
      searchText: '',
    }
  },
 computed: {
  products() {
    if (!this.filter) {
      return this.$root.$data.products.filter(product => product.name.toLowerCase().search(this.searchText.toLowerCase()) >= 0);
    }
    return this.$root.$data.products.filter(product => 
    product.genre === this.filter && 
    product.name.toLowerCase().search(this.searchText.toLowerCase()) >= 0);
  }
 },
};
</script>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

}
.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
  align-self:center;
}
form {
  display: table;
  width: 100%;
}
i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}
input {
  display: table-cell;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}
.genre-container {
  display: flex;
  align-self:center;
}
.menu-text {
  padding-top: 12px;
}
.footer{
    font-size:16px;
    width: 100%;
    height: 40px;
    position: fixed;
    bottom: 0;
    background-color: white;
}

</style>