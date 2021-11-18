<script context="module">
	import { storyblok } from '$lib/storyblok';

	/**
	 * @type {import('@sveltejs/kit').Load}
	 */
	export async function load({ fetch }) {
		const res = await storyblok.get('cdn/stories/home', { version: 'draft' });
		// console.log(res.data.story.content);
		if (res.data) {
			return {
				props: {
					bloks: res.data.story.content.body
					// subtitle: await res.data.story.content.body[0].subtitle
				}
			};
		}

		return {
			status: 404,
			error: new Error(`Could not load storyblok`)
		};
	}
</script>

<script>
	import Hero from '$lib/Bloks/Hero.svelte';
	import AboutMe from '$lib/Bloks/AboutMe.svelte';
	import Projects from '$lib/Bloks/Hero.svelte';
	const components = {
		Hero,
		'About Me': AboutMe,
		Projects
	};
	export let bloks;
	// console.log(bloks);
</script>

{#each bloks as blok}
	<svelte:component this={components[blok.component]} data={blok} />
{/each}

<section class="footer">
	<h3>Your next project here?</h3>
	<h4>Contact me</h4>
</section>

<style>
	h3 {
		font-family: Sang Bleu OG Sans;
	}

	/* .half {
		display: flex;
		flex-direction: column;
		align-items: center;
		flex: 1 1 0;
	} */
</style>
