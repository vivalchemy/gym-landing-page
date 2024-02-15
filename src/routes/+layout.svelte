<script>
	import '../app.css';
	import Footer from '/src/components/Footer.svelte';
	import CtAs from '/src/components/CTAs.svelte';
	import { openModal } from '../store';
	import Header from '../components/Header.svelte';

	let y;
	$: outerHeight = 0;

	function reroute(href) {
		$openModal = false;
		window.location.href = href;
	}
</script>

{#if $openModal}
	<div
		class="fixed top-0 left-0 w-screen h-screen border-b bg-white z-50 flex flex-col gap-8 p-5 px-8 md:hidden"
	>
		<div class="flex items-center justify-between gap-4 border-b pb-2 flex-1">
			<a href="/"
				><h1 class="font-semibold">Swoley <span class="text-indigo-400">Moley</span></h1></a
			>
			<button class="outline-none border-none" on:click={() => ($openModal = false)}
				><i class="fa-solid fa-xmark text-2xl"></i></button
			>
		</div>
		<div class="flex flex-col gap-4">
			<button
				class="border-none outline-none p-2 group duration-200 cursor-pointer text-left"
				on:click={() => {
					reroute('#products');
				}}
				><p class="duration-200 group-hover:pl-2 poppins text-3xl font-semibold">
					Product<i class="fa-solid fa-chevron-right text-xl pl-4" />
				</p></button
			>
		</div>
		<div class="flex flex-col gap-4">
			<button
				class="border-none outline-none p-2 group duration-200 cursor-pointer text-left"
				on:click={() => {
					reroute('#reviews');
				}}
				><p class="duration-200 group-hover:pl-2 poppins text-3xl font-semibold">
					Reviews<i class="fa-solid fa-chevron-right text-xl pl-4" />
				</p></button
			>
		</div>
		<div class="flex flex-col gap-4">
			<button
				class="border-none outline-none p-2 group duration-200 cursor-pointer text-left"
				on:click={() => {
					reroute('#faqs');
				}}
				><p class="duration-200 group-hover:pl-2 poppins text-3xl font-semibold">
					FAQs<i class="fa-solid fa-chevron-right text-xl pl-4" />
				</p></button
			>
		</div>
		<div class="flex flex-col items-center justify-center"></div>
		<CtAs />
	</div>
{/if}
{#if y > outerHeight}
  <div class="bg-white fixed top-0 left-0 w-full flex flex-col z-20 px-4 fadeIn"><Header/></div>
{/if}
<slot />
<Footer />
<svelte:window bind:scrollY={y} bind:outerHeight />
