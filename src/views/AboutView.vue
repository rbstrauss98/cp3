<template>
<div>
  <div class="title">
    <h1>How to Use this Website</h1>
  </div>
  <div class="content-container">
    <div>
      <p class="para">Thank you for choosing Books to check out your next read! 
      Here I will explain a little on how this website works.</p>
    </div>
    <div>
      <h3 class="sub-header">Main Navigation</h3>
          <p class="para">Clicking the main logo will return you to the main page and library</p>
    </div>
    <div>
      <h3 class="sub-header">Check Out</h3>
      <p class="para">Clicking on the "Check Out" button under a book will 
      add that book to your checkouts, and remove the book from the library. 
      You will see the Checkout Items button on the top right increment with each add.</p>
      <p class="para">Clicking on that same top right button will bring you to The Check Out page. 
      Here you can view the books you have checked out, 
      and you can remove them to return them back to the library</p>
      
    </div>
    <div>
      <h3 class="sub-header">Genre's and Search</h3>
      <p class="para">Clicking on any of the three Genre buttons will display the respective books of that genre, 
      and the searhc bar will work for the titles of the books. Filtering the books by genre and 
      searching from that genre works as well.</p>
    </div>
  </div>
  <div class="footer">
    <p class="footer-text">This is the link to my github repository for this lab: 
    <a href="https://github.com/rbstrauss98/cp3">repository</a>
    </p>   
  </div>
</div>
</template>

<script>

export default {
  name: 'AboutView',
}
</script>

<style scoped>
.title {
  text-align: center;
  font-size: 35px;
}

.para {
  font-size: 20px;
}
.sub-header {
  font-size: 30px;
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