<script>
  // @ts-nocheck

  let search = "";
  let cocktails = "";
  let errorMessage = "";

  export let data;
  const { drinks } = data;
</script>

<h1>Cocktails</h1>

<div class="cocktailGrid">
  {#each drinks as { strDrink, strDrinkThumb }}
    <card>
      <img src={strDrinkThumb} alt="" />
      <p>{strDrink}</p>
    </card>
  {/each}
</div>

<style>
  .cocktailGrid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-gap: 10px;
  }

  .cocktailGrid card {
    aspect-ratio: 1/1; /* Maintain a square aspect ratio for each card */
  }

  .cocktailGrid card img {
    width: 100%; /* Make the image fill the container */
    height: 100%;
    object-fit: cover; /* Maintain aspect ratio and cover the available space */
  }
</style>
