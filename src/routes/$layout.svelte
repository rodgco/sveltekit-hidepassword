<script>
  import "../app.css";
</script>

<header>
  <h1>Password Show/hide Demo</h1>
</header>

<main>
  <slot />
</main>

<footer>
  Jason M. Knight, 11 Feb 2021 - Svelte adaptation by Rodrigo Couto, 12 Apr 2021
</footer>

<style>
  header,
  footer {
    flex: 0 0 auto;
    padding: 1em;
    background: #048;
    color: #fff;
  }

  main {
    flex: 1 0 auto;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 1em;
  }
</style>
