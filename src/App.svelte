<script>
	import Options from "./Components/Options.svelte";
</script>

<section>
	<h1>Welcome to Shearch Movies and books!</h1>
	<h2>
		Made 100% to learn Svelte by <a
			href="https://github.com/Deyverson1"
			target="_blank"><span>@Deyverson1</span></a
		>, following one of
		<a href="https://github.com/midudev?tab=repositories" target="_blank"
			><span>@Midudev's</span></a
		> projects
	</h2>
	<Options />
</section>

<style>
	:root {
		--primary-color: #ffffff;
		--gray-medium: #4a5568;
		--gray-light: #9ca3af;
		--dark-turquoise: #00ced1;
	}
	section {
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
	}
	h1 {
		font-size: 48px;
		font-weight: 800;
		color: var(--primary-color);
	}
	h2 {
		font-size: 20px;
		font-weight: 300;
		color: var(--gray-light);
		max-width: 800px;
	}
	span {
		color: var(--dark-turquoise);
	}
	a {
		text-decoration: none;
	}
	span:hover {
		font-size: 21px;
	}
</style>
