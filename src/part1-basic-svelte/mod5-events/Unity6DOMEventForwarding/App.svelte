<script>
	import BigRedButton from './BigRedButton.svelte';
	

	function handleClick() {
		alert('Click')
	}
</script>

<BigRedButton on:click={handleClick} />