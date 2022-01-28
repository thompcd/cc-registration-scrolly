<script>
  import { themes } from '../config.js';
	import { getContext } from 'svelte';

	export let theme = getContext('theme');
	export let filled = false;
	export let center = true;
</script>

<nav style="border-bottom-color: {themes[theme]['muted']}; {filled ? 'background-color: ' +  themes[theme]['background'] + ';' : ''}">
  <div class="col-wide middle" class:center>
		<a href="https://sapulpatimes.com">
			<picture>
				{#if theme == 'dark'}
				<img src="./img/st-flat-white.png" alt="Sapulpa Times">
				{:else if filled == true}
				<img src="./img/st-flat-white.png" alt="Sapulpa Times">
				{:else}
				<img src="./img/st-flat-white.png" alt="Sapulpa Times">
				{/if}
			</picture>
		</a>
  </div>
</nav>

<style>
	nav {
		-webkit-box-sizing: border-box;
		box-sizing: border-box;
		position: relative;
		height: 73px;
		margin-bottom: -73px;
		border-bottom: 1px solid #777;
		z-index: 1;
	}
	picture {
		position: relative;
		top: -3px;
		padding: 0 5px;
	}
	img {
		height: 52px;
	}
	a img:hover {
		cursor: pointer;
	}
</style>