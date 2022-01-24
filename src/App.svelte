<!-- App.svelte -->
<script>
	import { Router, Link, Route } from "svelte-routing";
	import Home from "./routes/Home.svelte";
	import About from "./routes/About.svelte";
	import ArtAppr from "./routes/ArtAppr.svelte";

	export let url = "";
</script>

<Router {url}>
	<nav id="navbar">
		<Link to="/">Home</Link>
		|
		<Link to="/art_appr">Art Appreciation</Link>
		|
		<Link to="about">About</Link>
	</nav>
	<div id="render">
		<Route path="about" component={About} />
		<Route path="art_appr" component={ArtAppr} />
		<Route path="/"><Home /></Route>
	</div>
</Router>

<style>
	#navbar {
		text-align: center;
	}

	#render {
		width: 100%;
		height: 100%;
		margin: 0px;
		padding: 0px;
	}
</style>
