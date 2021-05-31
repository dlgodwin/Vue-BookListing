<template>
    <div>
        <h1>{{ title }}</h1>

        <ul>
            <book-item v-for="book in books" :book="book" :key="book.title">
            </book-item>
        </ul>

        <book-form @addBook="appendBook"></book-form>
    </div>
</template>

<script>
    import BookItem from "./BookItem";
    import BookForm from "./BookForm";

    export default {
        components: { 
            BookItem, 
            BookForm 
        },
        methods: {
            appendBook: function(bookTitle, bookAuthor) {
                this.books.push({ title: bookTitle, author: bookAuthor });
            }
        },
        name: "BookList",
        data() {
            return {
                title: "All Books",
                books: [
                    {title: 'Self-Reliance', author: 'Ralph Waldo Emerson'},
                    {title: 'American Gods', author: 'Neil Gaiman'},
                    {title: 'Amusing Ourselves to Death', author: 'Neil Postman'},
                ],
            }
        },
    }
</script>

<style>
    h1, h2 {
        font-weight: normal;
    }

    ul {
        list-style-type: none;
        padding: 0;
    }
</style>