<script>
	import { storyblok } from '$lib/storyblok';

	export let data;
	// console.log(data, render);
</script>

<section class="about-me">
	<div>
		{@html storyblok.richTextResolver.render(data.text)}
	</div>

	<div class="tags">
		{#each data.tags as tag}
			<a>{tag.label}</a>
		{/each}
	</div>
</section>

<style>
	.about-me {
		position: relative;
		padding: 8em;
		z-index: 2;
		/* height: 600px; */
		background: transparent linear-gradient(66deg, #2d7944 0%, #1b2860 100%) 0% 0% no-repeat
			padding-box;
		display: flex;
		gap: 8em;
		color: #f5f4ef;
	}
</style>
