<script>
	export let data;

	const links = [
		{ href: '/about-me', label: 'UX Design' },
		{ href: '/work', label: 'UI Design' },
		{ href: '/contact', label: 'Product Design' },
		{ href: '/contact', label: 'Behind the (inter)face', transparent: true }
	];
</script>

<section class="hero-container">
	<span class="pre-title">{data.pre_title}</span>

	<h1>{data.title}</h1>

	<h2>{data.subtitle}</h2>

	<div class="tags">
		{#each data.tags as tag}
			<a href={tag.href} class:transparent={tag.transparent}>
				{tag.label}
			</a>
		{/each}
	</div>

	<div class="hero">
		<div class="circle" />

		<img src={data.image.filename} alt={data.image.alt} />
	</div>

	<span class="banner">UX + UI + Product Design + Front-end Development</span>
</section>

<style>
	h1,
	h2 {
		color: #1d305d;
	}
	h1 {
		grid-area: 1 / 2 / 2 / 3;

		font-family: Sang Bleu OG Sans;
		font-size: 100px;
		line-height: 100px;
		margin: 0px;
	}
	h2 {
		grid-area: 2 / 2 / 3 / 3;

		font-family: Euclid Square;
		font-size: normal;
		font-weight: normal;
		margin-bottom: 32px;
		margin-top: 0;
	}
	.hero-container {
		display: grid;
		grid-template-columns: 1fr 2fr 3fr;
		grid-template-rows: min-content min-content min-content 0.2fr;
	}
	span.pre-title {
		grid-area: 1 / 1 / 2 / 2;
		font-size: 40px;
		line-height: 40px;
		opacity: 10%;
		text-align: right;
	}
	.hero {
		grid-area: 1 / 3 / 5 / 4;
		height: 720px;
		display: flex;
		align-items: flex-end;
		justify-content: center;
	}
	.banner {
		grid-area: 4 / 1 / 5 / 4;
		z-index: 2;
		display: flex;
		align-items: flex-end;
	}
	span.banner {
		text-align: center;
		vertical-align: text-bottom;
		font-family: Sang Bleu OG Sans;
		font-size: 60px;
		letter-spacing: 0px;
		color: #1d305d;
		opacity: 0.13;
		white-space: nowrap;
		overflow: hidden;
	}
	.tags > a.transparent {
		color: #1d305d;
		background: transparent;
		border: 2px solid #1d305d;
	}

	.circle {
		position: absolute;
		bottom: -4em;
		/* left: -4em;  */
		z-index: 1;
		background: rgb(191, 195, 204);
		background: linear-gradient(90deg, rgba(191, 195, 204, 1) 0%, rgba(196, 214, 197, 1) 100%);
		border-radius: 50%;
		width: 600px;
		height: 600px;
	}
	img {
		height: 600px;
		z-index: 3;
		position: relative;
	}
	.tags > a {
		background: transparent linear-gradient(155deg, #2d7944 0%, #1b2860 100%) 0% 0% no-repeat
			padding-box;
		border-radius: 100px;
		padding: 1em 2em;
		text-align: center;
		font: normal normal medium 16px/26px Euclid Square;
		letter-spacing: 0px;
		color: #ffffff;
		text-decoration: none;
	}

	.tags {
		grid-area: 3 / 2 / 4 / 3;
		display: flex;
		flex-wrap: wrap;
		gap: 18px;
	}
</style>
