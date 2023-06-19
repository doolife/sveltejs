<script>
	// https://github.com/sveltejs/template
	import {Router, Link, Route} from "svelte-routing";
	import Home from "./routes/Home.svelte";
	import About from "./routes/About.svelte";

	export let url = "";
</script>

<Router url="{url}">
	<nav class="navigation">
		<Link to="/">Home</Link>
		<Link to="about">About</Link>
	</nav>

	<div class="contents">
		<Route path="/"><Home /></Route>
		<Route path="about"><About /></Route>
	</div>
</Router>

<style>
	
</style>