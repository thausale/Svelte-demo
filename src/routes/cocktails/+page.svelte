<script>
  // @ts-nocheck

  let search = "";
  let cocktails = "";
  let errorMessage = "";

  const searchCocktail = async () => {
    errorMessage = "";
    cocktails = "";
    try {
      const response = await fetch(
        `http://www.thecocktaildb.com/api/json/v1/1/filter.php?i=${search}`
      );
      const data = await response.json();
      cocktails = data.drinks;
    } catch (error) {
      console.error(error);
      errorMessage = error;
    }
  };
</script>

<h1>Cocktails</h1>
<form action="" on:submit={searchCocktail}>
  <input type="text" bind:value={search} />
  {errorMessage}
</form>
<div class="cocktailGrid">
  {#each cocktails as { strDrink, strDrinkThumb }}
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
