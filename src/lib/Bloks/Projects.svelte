<section class="projects">
	<h3>Here's some of the stuff I've done</h3>

	{#each projects as project}
		<div class="project">
			<img src={project.img} alt={project.title} />
			<h3>{project.title}</h3>
			<p>{project.description}</p>
		</div>
	{/each}
</section>
