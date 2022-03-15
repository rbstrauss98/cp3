<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link style="text-decoration: none; color: inherit;" to="/">
        <img src="/images/books.logo.png">
      </router-link>
    </div>
    <div id="side">
      <router-link style="text-decoration: none; color: inherit;" to="/checkout">
        <div class="menu-item">
          <p>Check Out {{numItems}} item(s)</p>
        </div>
      </router-link>
      <router-link style="text-decoration: none; color: inherit;" to="/about">
        <div class="menu-item">
          <p>How to use this Website</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
</div>
</template>

<script>
export default {
  computed: {
    numItems() {
      return this.$root.$data.cart.length;
    },
  },
};
</script>


<style>
* {
  box-sizing: border-box;
}
body {
  margin: 50px 100px;
}
#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}
#menu a {
  color: #B84901;
}
#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}
#brand img {
  height: 200px;
}
#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}
#side img {
  width: 50px;
}
.menu-item {
  display: flex;
  flex-direction: column;
  height: 50px;
  background: #000;
  color: white;
  border: none;
  width: 100px;
  text-align: center;
  border: 1px solid white;
}
.menu-item p {
  margin: 0px;
}

</style>