<script lang="ts">
	import '../app.css';
	import IconMenu from '~icons/material-symbols-light/menu';
	import IconClose from '~icons/material-symbols-light/close';

	let dropdown = false;

	function handleDropdown() {
		dropdown = !dropdown
	} 
</script>

<!-- <Navbar class="bg-transparent border-transparent dark:bg-transparent dark:border-transparent">
	<NavBrand href="/">
		<img src={Icon} class="me-3 h-6 sm:h-9" alt="Svelte Logo" />
		<span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">Kairos Fellowship Church</span>
	</NavBrand>
	<NavHamburger />
	<NavUl>
		<NavLi href="/">Home</NavLi>
		<NavLi href="/about">About</NavLi>
		<NavLi href="/docs">Navbar</NavLi>
		<NavLi href="/pricing">Pricing</NavLi>
		<NavLi href="/contact">Contact</NavLi>
	</NavUl>
</Navbar> -->

<nav class="bg-transparent">
	<div class="bg-white mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
		<button on:click={handleDropdown}>
			{#if dropdown}
				<IconClose />
			{:else}
				<IconMenu />
			{/if}
		</button>
		{#if dropdown}
		Hey
		{/if}
		<ul>
			<li>
				<a href="/">Home</a>
			</li>
			<li>
				<a href="about">About</a>
			</li>
		</ul>
	</div>
</nav>


<slot />
