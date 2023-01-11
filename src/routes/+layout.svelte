<script>
	import '../app.css';
	import { Navbar, NavBrand, NavLi, NavUl, NavHamburger } from 'flowbite-svelte';
	import {
		Footer,
		FooterBrand,
		FooterCopyright,
		FooterIcon,
		FooterLink,
		FooterLinkGroup
	} from 'flowbite-svelte';
	import { DarkMode } from 'flowbite-svelte';

	let btnClass =
		'text-gray-500 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-700 rounded-full text-sm p-1 absolute right-0 top-2';
</script>

<DarkMode {btnClass} />
<div class="container mx-auto px-4">
	<Navbar let:hidden let:toggle>
		<NavBrand href="/">
			<span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">
				Feed the Search
			</span>
		</NavBrand>
		<NavHamburger on:click={toggle} class="absolute right-6" />
		<NavUl {hidden}>
			<NavLi href="/" active={true}>Home</NavLi>
			<NavLi href="/about">About</NavLi>
			<NavLi href="/services">Services</NavLi>
			<NavLi href="/pricing">Pricing</NavLi>
			<NavLi href="/contact">Contact</NavLi>
		</NavUl>
	</Navbar>
</div>
<div class="container mx-auto px-4">
	<slot />
</div>

<div class="container mx-auto px-4">
	<Footer>
		<FooterCopyright href="/" by="Feed the Search™" year={2023} />
		<FooterLinkGroup
			ulClass="flex flex-wrap items-center mt-3 text-sm text-gray-500 dark:text-gray-400 sm:mt-0"
		>
			<FooterLink href="/">About</FooterLink>
			<FooterLink href="/">Privacy Policy</FooterLink>
			<FooterLink href="/">Licensing</FooterLink>
			<FooterLink href="/">Contact</FooterLink>
		</FooterLinkGroup>
	</Footer>
</div>
