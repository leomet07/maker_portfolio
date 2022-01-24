<script>
	import ArtWork from "../components/ArtWork.svelte";
	const art_works = [
		{
			title: "Paper Bag",
			how: "Pencil on Paper",
			when: "2021",
			dimensions: `12" by 9"`,
			img_src: "/img/art_appr/paper_bag.jpg",
		},
		{
			title: "Figure Drawing",
			how: "Pencil on Paper",
			when: "2021",
			dimensions: `15" by 10.5"`,
			img_src: "/img/art_appr/figure_drawing.jpg",
		},
	];
</script>

<main>
	<h1 id="title">Art Appreciation</h1>
	<h2>Ms. Leo's Period 4 Fall Semester 2021-2022</h2>
	<section id="artwork_display">
		{#each art_works as work, index}
			<div class="artwork">
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
</main>

<style>
	main {
		text-align: center;
	}
	#artwork_display {
		width: 100%;
		margin-top: 10px;
	}
	.artwork {
		margin-bottom: 10vh;
	}
</style>
