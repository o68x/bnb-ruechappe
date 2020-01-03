<script>
	import Banner from "./banner.svelte"
	import topics from './topics.json'
	$: console.log(typeof title)
	export let name;
</script>

<main>
	<Banner />
	<div class="cards">
		<!-- TODO:  -->
		<ul>
			{#each topics as {userId, id, title, body} }
			<li>
			<b>{id} {title}:</b> {body}
			</li>
			{/each}
		</ul>
	</div>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
