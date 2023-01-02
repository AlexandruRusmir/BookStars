<script>
    import { push } from 'svelte-spa-router';
    export let book;

    const viewBookDetailsPage = () => {
        push(`#/book_details/${book.id}`);
    }
</script>

<div>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <div class="book-card" on:click={viewBookDetailsPage}>
        <p>Title: {book.name}</p>
        <p>Author: {book.author}</p>
        <div class="d-flex align-items-center justify-content-center">
            <img class="book-image" src={book.imageUrl} alt="Book"/>
        </div>
    </div>
</div>

<style>
    .book-card {
        padding: 10px;
        width: 300px;
        height: 400px;
        border-radius: 8px;
        background-color: #080a3f;
        color: #ffffff;
    }

    .book-card:hover {
        cursor: pointer;
        filter: drop-shadow(0 0 0.5em #646cffaa);
    }

    .book-image {
        max-height: 300px;
        max-width: 300px;
    }
</style>