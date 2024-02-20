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

<main>
	<div id="nav" class="container relative flex justify-between bg-transparent p-2">
		<div class="content-center text-5xl">
			<IconClose class="m-1 fill-current" />
			<button class="flex IconClose" on:click={handleDropdown}>
				{#if dropdown}
					<div in:fade={{ duration: 300 }}>
						<IconClose class="IconClose"/>
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
		<nav>
			<div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
				<div class="relative flex h-16 items-center justify-between">
					<div class="flex justify-between">
						<ul>
							<li>
								<a href="/">Home</a>
							</li>
							<li>
								<a href="about">About</a>
							</li>
						</ul>
					</div>
				</div>
			</div>
		</nav>
	</div>
	
	<slot />
</main>

<style lang="css">
	a {
		@apply text-3xl underline;
	}

	.IconClose {
		@apply text-white;
	}
</style>
