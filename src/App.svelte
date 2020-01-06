<script>
  import Header from "./header.svelte"
  import Footer from "./footer.svelte"
  import Card from "./card.svelte"
  import cards from './cards.json'
  $: console.log(typeof title)
</script>

<style>
  main {
    margin: 0 auto;
  }

  .cards {
    display: grid;
    /*  REF: Responsive without media-queries! 😄
        https://css-tricks.com/look-ma-no-media-queries-responsive-layouts-using-css-grid/
    */
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    grid-auto-rows: minmax(240px, auto);
    align-content: start;
    grid-gap: 40px;
    min-height: calc(100vh - 10em); /* removes header and footer height */
    max-width: 1200px;
    margin: auto;
    }
</style>

<main>
  <Header />
  <div class="cards">
      {#each cards as {title, body} }
      <Card>
      <span slot="title">{title}</span>
      <span slot="body">{@html body}</span>
      </Card>
      {/each}
  </div>
  <Footer />
</main>

