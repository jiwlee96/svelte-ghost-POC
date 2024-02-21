<script lang="ts">
	import '../app.css';
	import { fade } from 'svelte/transition';
	import IconMenu from '~icons/material-symbols-light/menu';
	import IconClose from '~icons/material-symbols-light/close';

	let dropdown = false;

	function handleDropdown() {
		dropdown = !dropdown;
	}
</script>

<!-- Start of the Header NavBar -->
<div id="headernav" class="relative flex justify-end bg-transparent p-2">
	<!-- Horizontal NavBar -->
	<nav class="flex justify-end">
		<ul>
			<li>
				<a href="/">Home</a>
			</li>
			<li>
				<a href="about">About</a>
			</li>
			<li>
				<a href="sermons">Sermons</a>
			</li>
			<li>
				<a href="contact">Contact Us</a>
			</li>
		</ul>
	</nav>
	<!-- 
	SideBar Menu

	Active on sm or below
	-->
	<div class="flex sm:hidden">
		<button class="icon-preset flex" on:click={handleDropdown}>
			{#if dropdown}
				<div in:fade={{ duration: 300 }}>
					<IconClose />
				</div>
			{:else}
				<div in:fade={{ duration: 300 }}>
					<IconMenu />
				</div>
			{/if}
		</button>
		{#if dropdown}
			<div class="testing" transition:fade={{ duration: 300 }}>Hey</div>
		{/if}
	</div>
</div>

<slot />

<style lang="css">
	a {
		@apply text-xl;
	}

	ul > li {
		@apply inline-block
		p-1;
	}

	.icon-preset {
		@apply my-auto text-2xl
	text-white;
	}
</style>
