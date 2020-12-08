<script>
	import { Nav, NavItem, NavLink } from "sveltestrap";
	export let name;
</script>

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

<main>
	<Nav>
		<NavItem>
			<NavLink href="#">Link</NavLink>
		</NavItem>
		<NavItem>
			<NavLink href="#">Link</NavLink>
		</NavItem>
		<NavItem>
			<NavLink href="#">Another Link</NavLink>
		</NavItem>
		<NavItem>
			<NavLink disabled href="#">Disabled Link</NavLink>
		</NavItem>
	</Nav>
	<h1>Aloha {name}!</h1>
	<p>
		Visit the
		<a href="https://svelte.dev/tutorial">Svelte tutorial</a>
		to learn how to build Svelte apps.
	</p>
</main>
