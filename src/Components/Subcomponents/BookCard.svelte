<script>
    import { push } from 'svelte-spa-router';
    export let bookId;
    export let title;
    export let author;

    const viewBookDetailsPage = () => {
        push(`#/book_details/${bookId}`);
    }
</script>

<div>
    <button class="book-card" on:click={viewBookDetailsPage}>
        <p>Title: {title}</p>
        <p>Author: {author}</p>
    </button>
</div>

<style>
    .book-card {
        margin: 10px;
        padding: 10px;
        max-width: 300px;
        border-radius: 8px;
        background-color: #080a3f;
        color: #ffffff;
    }

    .book-card:hover {
        filter: drop-shadow(0 0 0.5em #646cffaa);
    }
</style>