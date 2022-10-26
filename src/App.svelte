<script>
  import svelteLogo from './assets/svelte.svg'
  import NavBar from './Components/NavBar.svelte';

  import Router from 'svelte-spa-router';
  import Home from './Components/Home.svelte';
    import MyBooks from './Components/MyBooks.svelte';
    import NotFound from './Components/NotFound.svelte';
    import BookDetails from './Components/Subcomponents/BookDetails.svelte';
    import AllBooks from './Components/AllBooks.svelte';

    const routes = {
        '/': Home,
        '/all_books': AllBooks,
        '/my_books': MyBooks,
        '/book_details/:id': BookDetails,

        '*': NotFound
    }
</script>

<main>
  <NavBar />
  <div class="page-container">
    <Router {routes} />
  </div>
  
</main>

<style>
  .page-container {
    margin-top: 100px;
  }

  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
