<script lang="ts">
	import '../app.css';
	import Icon from '$lib/assets/favicon.png';
	import { Navbar, NavBrand, NavHamburger, NavUl, NavLi } from 'flowbite-svelte';
	import NavContainer from 'flowbite-svelte/NavContainer.svelte';
</script>

<Navbar class="bg-transparent border-transparent dark:bg-transparent dark:border-transparent">
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
</Navbar>

<slot />
