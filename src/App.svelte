<script>
	import TextArea from "./components/TextArea.svelte"
	import Button from "./components/Button.svelte"
	let jobDesctiption = "";

	function handleSubmit(e) {
		console.log(jobDesctiption);
	}
</script>

<main>
	<h2>Wordalo!</h2>
	<p>
		Our purpose here is to be simple and useful.
	</p>
	<div class="buttons_area">
		<div class="mini-btn linkedin">
			Linkedin
		</div>
		<div class="mini-btn glassdoor">
			Glassdoor
		</div>
		<div class="mini-btn indeed">
			Indeed
		</div>
		<div class="mini-btn paste">
			Paste
		</div>
		<!-- Maybe they are not only using this service for jobs? -->
	</div>
	<form on:submit|preventDefault={handleSubmit}>
		<TextArea 
			bind:value={jobDesctiption}
			placeholder="Enter job description or simply click on paste button at the top!" 
		/>
		<Button text="Search"/>
	</form>
</main>

<style>
	main {
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	form {
		all:revert;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.buttons_area {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		width: 400px;
		gap: 10px;
		padding: 10px;
		/* border: 2px solid #333; */
	}

	.mini-btn {
		padding: 10px;
		border-radius: 3px;
		text-align: center;
		cursor: alias;
	}

	.linkedin {
		background-color: #2667B3; 
		color: #fff
	}

	.glassdoor {
		background-color: #0CAA41; 
		color: #fff
	}

	.indeed {
		background-color: #002A3A; 
		color: #fff
	}

	.paste {
		background-color: rgb(92, 0, 0); 
		color: #fff
	}
</style>
