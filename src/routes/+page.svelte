<script lang="ts">
	import { Textarea, Button } from "flowbite-svelte";

	let bookText = "";
	let cipherText = "";
	let output = "";

	function decode() {
		const book = bookText.split(/\s+/);
		output = cipherText.replace(/(\d+?)\/(\d+?)/g, (match, ..._) => {
			const [word, letter] = match.split("/");
			const wordIndex = parseInt(word) - 1;
			const letterIndex = parseInt(letter) - 1;
			return book[wordIndex][letterIndex];
		});
	}
</script>

<div class="p-3 flex h-screen w-screen flex-col gap-3 items-center">
	<p class="m-5 mt-4 text-lg text-white">Book cipher</p>

	<div class="flex gap-3 w-full flex-grow">
		<Textarea id="book" placeholder="Book text..." bind:value={bookText} />
		<Textarea id="cipher" placeholder="Cipher text..." bind:value={cipherText} />
	</div>

	<Button class="px-10" on:click={decode}>Decode</Button>

	<div class="flex justify-center w-full">
		<Textarea id="output" rows="12" placeholder="Output" bind:value={output}></Textarea>
	</div>
</div>

<style>
	:global(body) {
		background-color: #111827;
	}
</style>
