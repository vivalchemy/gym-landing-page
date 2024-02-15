<script>
	import { openModal } from '../store';
</script>

<header class="flex flex-col relative z-20">
	<div class="max-w-[1400px] mx-auto w-full flex items-center justify-between px-4 py-6">
		<a href="/"><h1 class="font-semibold">Swoley <span class="text-indigo-400">Moley</span></h1></a>
		<nav class="hidden md:flex items-center gap-4 lg:gap-6">
			<a href="#products" class="duration-200 hover:text-indigo-400 cursor-pointer">Products</a>
			<a href="#reviews" class="duration-200 hover:text-indigo-400 cursor-pointer">Reviews</a>
			<a href="#faqs" class="duration-200 hover:text-indigo-400 cursor-pointer">FAQs</a>
			<button class="specialBtn">
				<p>Start free today</p>
			</button>
		</nav>
		<button class="md:hidden grid place-items-center" on:click={() => ($openModal = true)}
			><i class="fa-solid fa-bars"></i></button
		>
	</div>
</header>
