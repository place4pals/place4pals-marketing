<script lang="ts">
	import { Router, Route, Link } from "svelte-routing";
	import { onMount } from "svelte";
	import { fade } from "svelte/transition";
	import NavLink from "./components/NavLink.svelte";
	import Home from "./routes/Home.svelte";
	import Faq from "./routes/Faq.svelte";
</script>

<Router>
	<main>
		<logo>
			<Link to="/">
				<logoLink>
					<img
						height="50"
						width="50"
						alt=""
						src="logo.svg"
						style="margin-right:10px;"
					/>
					place4pals
				</logoLink>
			</Link>
			<nav>
				<NavLink to="/">Home</NavLink> |
				<NavLink to="/faq">FAQ</NavLink> |
				<a
					class="link"
					target="_blank"
					href="https://github.com/place4pals">GitHub</a
				>
				|
				<a
					class="link button not-mobile"
					href="https://app.p4p.io">Log In</a
				>
				<a
					class="link button button not-mobile"
					href="https://app.p4p.io/signup">Sign Up</a
				>
				<a
					class="link button only-mobile"
					on:click={() => {
						alert(
							`Sorry, this app isn't available for mobile devices yet. Visit this page on desktop instead!`
						);
					}}
					href="/#">download the app</a
				>
			</nav>
		</logo>
		<Route path="/" component={Home} />
		<Route path="faq" component={Faq} />
	</main>
	<footer>© {new Date().getFullYear()} place4pals</footer>
</Router>

<style>
	main {
		margin: auto;
		max-width: 1180px;
		min-height: calc(100vh - 100px);
	}
	logo {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: space-between;
	}
	logoLink {
		cursor: pointer;
		display: flex;
		flex-direction: row;
		align-items: center;
		font-size: 50px;
		font-weight: 100;
		pointer-events: none;
		transform: none;
	}
	footer {
		padding: 20px;
		color: #aaaaaa;
		font-size: 10px;
		text-align: center;
	}
	nav {
		color: #444444;
	}
	@media (max-width: 640px) {
		main {
			max-width: 100%;
			min-height: calc(100vh - 200px);
		}
		footer {
			width: unset;
		}
		logo {
			flex-direction: column;
		}
		nav {
			margin-top: 10px;
		}
	}
</style>
