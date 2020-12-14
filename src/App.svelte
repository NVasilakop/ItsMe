<script>
	import {
		Nav,
		NavItem,
		NavLink,
		Modal,
		ModalBody,
		ModalFooter,
		ModalHeader,
		Button,
	} from "sveltestrap";
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
	import Footer from "./Footer.svelte";
	import Contact from "./Contact.svelte";
	export let url = ""; //This property is necessary declare to avoid ignore the Router
	export let name;
	export let cookieModal = false;
	function takeTheCookie() {
		cookieModal = true;
	}

	function closeTheCookie() {
		cookieModal = false;
	}
</script>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}
	.leMargin {
		margin-bottom: 300px;
	}
	.navItem {
		margin-right: 10px;
	}

	.rotate {
		animation: rotation 8s infinite linear;
	}

	.cookieHeader {
		justify-content: center;
	}

	@keyframes rotation {
		from {
			transform: rotate(0deg);
		}
		to {
			transform: rotate(359deg);
		}
	}

	/* @keyframes move{
		from{

		}
		to{

		}
	} */
	/* #pot{bottom:15%;
position:absolute;
-webkit-animation:linear infinite alternate;
-webkit-animation-name: run;
-webkit-animation-duration: 5s;
}      */
	@keyframes run {
		0% {
			left: 0;
		}
		50% {
			left: 100%;
		}
		100% {
			left: 0;
		}
	}
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
		<Nav>
			<div class="navItem">
				<NavItem class="navItem">
					<Link to="/">Home</Link>
				</NavItem>
			</div>
			<div class="navItem">
				<NavItem class="navItem">
					<Link to="about">About</Link>
				</NavItem>
			</div>
		</Nav>
		<div>
			<Route path="about" component={About} />
			<!--for now the router just support case sensitive,
        one workaround colud be add two time the route
        Example.
       <Route path="About" component="{About}" /> 
	-->
			<img
				src="assets/cookie.png"
				alt=""
				class="rotate"
				width="50"
				height="50"
				on:click={takeTheCookie} />
			{#if cookieModal}
				<Modal isOpen={cookieModal}>
					<ModalHeader>
						<p class="cookieHeader">Cookie Of The Day</p>
					</ModalHeader>
					<ModalBody>You got bamboozled</ModalBody>
					<ModalFooter>
						<Button on:click={closeTheCookie}>
							Come tomorrow for another cookie
						</Button>
					</ModalFooter>
				</Modal>
			{/if}
			<Route path="/">
				<Home />
			</Route>
			<Route path="about/work" component={Work} />
			<Route path="about/interests" component={Interests} />
			<Route path="about/studies" component={Studies} />
			<Route path="contact" component={Contact} />
		</div>
		<div class="leMargin" />
		<Footer />
	</Router>
</main>
