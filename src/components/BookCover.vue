<template>
<router-link :to="{ name: 'Book', params: {id: book.id } }">  
    <div class="book-cover" :style="{ 'background-color': book.color}">
        <div class="spacer"></div>
        <div class="text-box">
            
            <h1 class="title">{{book.title}}</h1>
            <p class="author">{{book.author}}</p>
        </div>
    </div>
</router-link>
</template>
<script>
export default {
name: 'BookCover',
props: {
    // id: Number,
    // title: String,
    // author: String,
    // color: String,
    book: Object

},
    
}
</script>

<style lang="scss" scoped>



.book-cover{
    display: flex;
    align-items: flex-end;
    // background-color: tomato;

.spacer{
    margin-left: 2rem;
    height: 400px;
    width: 5px;
    background-color: rgba($color: #000000, $alpha: 0.2);
}
    .text-box{
        margin-left: 1rem;
        margin-bottom: 1rem;
        text-align: left;
        padding: 1rem;
        color: black;
        
        
        h1{
            margin: 0;
            font-size: 1.5rem;
            text-decoration: none;
        }
        p{
            margin: 0;
            margin-top: 0.5rem;
        }
   
    }
}
</style>