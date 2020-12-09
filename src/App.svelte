<script>
	import { Nav, NavItem, NavLink } from "sveltestrap";
	import { Router, Route, Link } from "svelte-routing";
	import { alert, defaultModules, defaults, info } from "@pnotify/core";
	import * as Confirm from "@pnotify/confirm";
	// import "@pnotify/core/dist/Angeler.css";

	// or

	// defaults.closerHover = false;

	import Home from "./Home.svelte";
	import About from "./About.svelte";
	import Work from "./Work.svelte";
	import Studies from "./Studies.svelte";
	import Interests from "./Interests.svelte";
	export let url = ""; //This property is necessary declare to avoid ignore the Router
	export let name;
	// PNotify.notice({
	// 	// t: "Non-Blocking Notice",
	// 	text: "This app is written in Svelte :D !!",
	// 	addModelessClass: "nonblock",
	// });
	info({
		title: "About this App",
		text: "This app is written in Svelte !!",
		modules: new Map([
			[
				Confirm,
				{
					confirm: true,
					buttons: [
						{
							text: "Ok",
							primary: true,
							click: (notice) => {
								notice.close();
							},
						},
					],
				},
			],
		]),
	});
</script>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	/* h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	} */

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>

<main>
	<!-- <Nav>
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
	</p> -->
	<Router {url}>
		<nav>
			<Link to="/">Home</Link>
			<Link to="about">About</Link>
		</nav>
		<div>
			<Route path="about" component={About} />
			<!--for now the router just support case sensitive,
        one workaround colud be add two time the route
        Example.
       <Route path="About" component="{About}" /> 
    -->
			<Route path="/">
				<Home />
			</Route>
			<Route path="about/work" component={Work} />
			<Route path="about/interests" component={Interests} />
			<Route path="about/studies" component={Studies} />
		</div>
	</Router>
</main>
