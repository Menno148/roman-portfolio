<script>
	const links = [
		{ href: '/', label: 'about me' },
		{ href: '/work', label: 'work' },
		{ href: '/contact', label: 'contact' }
	];
</script>

<nav>
	<!-- <span>Roman</span> -->
	{#each links as link}
		<a href={link.href}>
			{link.label}
		</a>
	{/each}
</nav>

<style>
	nav {
		height: 8em;
		padding: 0 8em;
		display: flex;
		flex-wrap: nowrap;
		align-items: center;
		justify-content: flex-end;
		gap: 4em;
	}

	span {
		text-align: center;
		font: normal normal normal 257px/364px SangBleu OG Sans Trial;
		letter-spacing: 0px;
		color: #1d305d;
		opacity: 0.01;
		position: absolute;
		right: 50px;
		top: -120px;
		user-select: none;
	}

	a {
		font-family: Euclid Square;
		font-size: 1.1em;
		color: #1d305d;
		text-decoration: none;
	}

	a::after {
		content: '';
		width: 0px;
		height: 1px;
		display: block;
		background: #1d305d;
		transition: 300ms;
	}
	a:hover::after {
		width: 100%;
	}

	/* a:visited {
    color: 
  } */
</style>
