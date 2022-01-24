<script>
	import ArtWork from "../components/ArtWork.svelte";

	const art_works = [
		{
			title: "Architectural Sculpture",
			how: "Recycled cardboard and foam",
			when: "2022",
			dimensions: `9" by 26" by 9"`,
			img_src: "/img/art_appr/bridge.jpg",
		},
		{
			title: "Met Project",
			how: "Colored pencils on paper",
			when: "2021",
			dimensions: `11" by 8.5"`,
			img_src: "/img/art_appr/met_project_preview.jpg",
		},
		{
			title: "Self Portrait",
			how: "Pencil and pastels on paper",
			when: "2021",
			dimensions: `11" by 8.5"`,
			img_src: "/img/art_appr/self_portrait.jpg",
		},
		{
			title: "Paper Bag",
			how: "Pencil on paper",
			when: "2021",
			dimensions: `12" by 9"`,
			img_src: "/img/art_appr/paper_bag.jpg",
		},
		{
			title: "Figure Drawing",
			how: "Pencil on paper",
			when: "2021",
			dimensions: `15" by 10.5"`,
			img_src: "/img/art_appr/figure_drawing.jpg",
		},
	];

	async function animateTo(art_name) {
		const id = "artwork_" + art_works.findIndex((v) => v.title == art_name);
		document.getElementById(id).scrollIntoView({ behavior: "smooth" });
	}
</script>

<main>
	<h1 id="title">Art Appreciation</h1>
	<h2>Ms. Leo's Period 4 Fall Semester 2021-2022</h2>
	<nav id="artwork_nav">
		<span
			on:click={() => {
				animateTo("Paper Bag");
			}}
			>Paper Bag Value Drawing
		</span>
		|
		<span
			on:click={() => {
				animateTo("Figure Drawing");
			}}>Figure Drawing</span
		>
		|
		<span
			on:click={() => {
				animateTo("Self Portrait");
			}}>Self Portrait</span
		>
		|
		<span
			on:click={() => {
				animateTo("Architectural Sculpture");
			}}>Architectural Sculpture</span
		>
		|
		<span
			on:click={() => {
				animateTo("Met Project");
			}}>Image from Met Project</span
		>
	</nav>
	<section id="artwork_display">
		{#each art_works as work, index}
			<div class="artwork" id={"artwork_" + index}>
				<ArtWork
					title={work.title}
					how={work.how}
					when={work.when}
					dimensions={work.dimensions}
					img_src={work.img_src}
					direction={index % 2 == 0 ? "row" : "row-reverse"}
				/>
			</div>
		{/each}
	</section>
	<p id="easter_egg">Did you like the work :)?</p>
</main>

<style>
	main {
		text-align: center;
	}
	#artwork_display {
		width: 100%;
		margin-top: 10px;
	}

	#artwork_nav span {
		text-decoration: underline;
		cursor: pointer;
		font-size: 1.2rem;
	}
	#easter_egg {
		padding-top: 20vh;
		padding-bottom: 2vh;
	}
</style>
