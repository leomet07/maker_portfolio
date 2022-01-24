<script>
	import { Link } from "svelte-routing";
</script>

<main>
	<h1 id="title">Leonid Metlitsky's Maker Portfolio</h1>
	<p id="name_ask">But <b>please</b>, call me Lenny</p>
	<section id="class_list">
		<h3>Courses I've taken:</h3>
		<div>
			<Link to="/art_appr">Art Appreciation</Link>
		</div>
	</section>
</main>

<style>
	main {
		text-align: center;
	}

	#name_ask {
		font-size: 1.5rem;
	}
	#class_list {
		margin-top: 20px;
		font-size: 1.3rem;
	}
</style>
