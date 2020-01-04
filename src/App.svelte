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
    <!-- TODO:  -->
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
    max-width: 240px;
    margin: 0 auto;
  }

  .cards {
    display: grid;
    grid-template-columns: 1fr 1fr;
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
