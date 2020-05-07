<template>
  <div class="home">
    <header>
      <h1>BookJack</h1>
    </header>
    <div class="grid-container">

     
      
      <BookCover v-for="(book, index) in localbooks" v-bind:key="index" :book="book"/>
      

    </div>
    <footer>

    </footer>
    
  </div>
</template>

<script>
// @ is an alias to /src
import BookCover from '../components/BookCover'

export default {
  name: 'Home',
  components: {
    BookCover,
  },
  
  data() { 
    return{
      localbooks: this.$root.books
    }
  },
    
}
</script>

<style lang="scss" scoped>

.grid-container{
  height: 800px;
 display: grid;
 grid-template-columns: repeat(4, 1fr);
 grid-template-rows: repeat(2, 1fr);
 gap: 1rem;
}

footer{
  height: 100px;
}

</style>
