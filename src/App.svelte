<script>
  import Header from "./header.svelte"
  import Footer from "./footer.svelte"
  import Card from "./card.svelte"
  import cards from './cards.json'
  $: console.log(typeof title)
</script>

<main>
  <Header />
  <div class="cards">
      {#each cards as {title, body} }
      <Card>
      <span slot="title">{title}</span>
      <span slot="body">{body}</span>
      </Card>
      {/each}
  </div>
  <Footer />
</main>

<style>
  main {
    margin: 0 auto;
  }

  .cards {
    display: grid;
    /*
    REF: Responsive without media-queries! 😄
    https://css-tricks.com/look-ma-no-media-queries-responsive-layouts-using-css-grid/
    */
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    grid-auto-rows: minmax(200px, auto);
    align-content: start;
    min-height: calc(100vh - 8em); /* removes header and footer height */
    margin: 0;
    padding: 0;
    }

  .cards ul li {
    list-style: none;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
