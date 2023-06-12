<script>
  import { goto } from "$app/navigation";
</script>

<nav>
  <a href="/todo">todo</a>
  <a href="/cocktails">cocktails</a>
  <a href="/preloaded-cocktails">preloaded cocktails</a>
</nav>

<slot />

<style>
  nav {
    width: 100vw;
    height: 5vh;
    background-color: rgb(201, 201, 201);
    padding: 0;
  }
</style>
