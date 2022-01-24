<script>
	export let title, img_src, how, dimensions, when, direction;
</script>

<div class="artwork_container" style={"flex-direction: " + direction}>
	<div>
		<h3>{title}</h3>
		<p>{how}</p>
		<p>{dimensions}</p>
		<p>{when}</p>
	</div>
	<img class="preview_img" src={img_src} alt={title} />
</div>

<style>
	.artwork_container {
		width: 100%;
		max-width: 600px;
		/* border: 1px solid gray; */
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin: auto;
		padding-top: 5vh;
		padding-bottom: 5vh;
	}
	.preview_img {
		width: 60%;
	}

	@media only screen and (max-width: 500px) {
		.artwork_container {
			display: block;
		}
		.preview_img {
			width: 90%;
		}
	}
</style>
