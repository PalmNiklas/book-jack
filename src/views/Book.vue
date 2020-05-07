<template>
  <div class="book">
    <header>
      <router-link to="/">GO BACK</router-link>

    </header>
    <main>
      <BookCover  :book="localbooks[$route.params.id -1]"/>
      <article class="content-container">
        <h1 class="title">{{localbooks[$route.params.id -1].title}}</h1>
        <h2 class="author">{{localbooks[$route.params.id -1].author}}</h2>
        <p>{{localbooks[$route.params.id -1].plot}}</p>
        <article class="meta-info-container">
          <div>
            <p class="audience"> <em>Audience:</em> {{localbooks[$route.params.id -1].audience}}</p>
            <p class="pages"><em>Pages:</em> {{localbooks[$route.params.id -1].pages}}</p>
          </div>
          <div>
            <p class="published"><em>Published:</em> {{localbooks[$route.params.id -1].year}}</p>
            <p class="publisher"><em>Publisher:</em>{{localbooks[$route.params.id -1].publisher}}</p>
          </div>
        </article>
        <button>Oh I want to read it</button>
      </article>
    </main>
    <footer>
      
    </footer>
    
    
  </div>
</template>

<script>
import BookCover from "../components/BookCover";

export default {
  name: 'BookInfo',

  components: {
    BookCover,
  },

  props: {
    
  },
  data(){
    return {
      localbooks: this.$root.books
    }
  }
  
}
</script>

<style lang="scss" scoped>

.book{
  width: 100vw;
  height: 100vh;
  background-color: #24252a;

  header{
    height: 10vh;
    display: flex;
    align-items: center;
    padding-left: 5rem;
  }

  main{
    height: 80vh;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    padding-left: 5rem;
    padding-right: 5rem;
    column-gap: 2.5rem;

    .content-container{
      text-align: left;
      
      h1{
        color: white;
        font-size: 4rem;
        margin: 0;
      }

      h2{
        color: grey;
        margin: 0;
      }
      p{
        color: grey;
        line-height: 1.5rem;
      }


      .meta-info-container{
        padding: 1rem;
        background-color: #2e3131;
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        column-gap: 1rem;
        color: grey;

        em{
          font-style: normal;
          font-weight: bold;
          color: white;
        }
      }
    }
  }

footer{
  height: 10vh;
}

button{
  margin-top: 2rem;
}
}

</style>
