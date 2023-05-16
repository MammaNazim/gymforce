<!-- LandingPage.svelte -->
<script lang="ts">
	import { onMount } from 'svelte';
	import { fade } from 'svelte/transition';
    import Saos from "/node_modules/saos";

	let showContent = false;
	let isHovered = false;

	let y: number;
	$: console.log(y);

	onMount(() => {
		showContent = true;
	});
	import About1 from './about1.svelte';
	import About2 from './about2.svelte';
	import About3 from './about3.svelte';
</script>

<svelte:window bind:scrollY={y} />

<main>
	<div class="part1">
		<div class=" h-screen flex items-center justify-center">
			{#if showContent}
				<div
					transition:fade={{ duration: 500, delay: 0 }}
					class="text-white text-center hover:bg-green-500 bg-transparent transition-colors duration-300 py-8 px-6 rounded-2xl"
					on:mouseenter={() => (isHovered = true)}
					on:mouseleave={() => (isHovered = false)}
				>
					<h1 class="text-4xl font-bold">GYMFORCE</h1>
					<p class="text-lg font-semibold mt-4">A gym tailored for all your needs</p>
					<div class="mt-4 flex items-center justify-center">
						<div class="rounded-full p-2">
							<a href="#about1">
								<svg
									class="w-16 h-16 transition-all duration-300 cursor-pointer rounded-full hover:bg-green-500 hover:opacity-80 animate-pulse transform hover:scale-125"
									fill="none"
									xmlns="http://www.w3.org/2000/svg"
									viewBox="0 0 24 24"
									stroke="currentColor"
								>
									<path
										stroke-linecap="round"
										stroke-linejoin="round"
										stroke-width="2"
										d="M19 14l-7 7m0 0l-7-7m7 7V3"
									/>
								</svg>
							</a>
						</div>
					</div>
				</div>
			{/if}
		</div>
		<div id="about1">
			<Saos
				animation={'fade-in 1.2s cubic-bezier(0.390, 0.575, 0.565, 1.000) both'}
				animation_out={'slide-out-fwd-center 0.7s cubic-bezier(0.550, 0.085, 0.680, 0.530) both'}
				top={250}
				bottom={250}
			>
				<About1 />
			</Saos>

		</div>
	</div>
		<div id="about2">
			<About2/>
		</div>
		<div id="about3">
			<About3/>
		</div>
</main>

<style>
	.part1 {
		height: 200vh;
		background-attachment: fixed;
		background-image: url('./src/images/lpbg.JPG');
		background-repeat: no-repeat;
		background-size: cover;
		background-position: center;
	}

	@keyframes -global-fade-in {
		0% {
			opacity: 0;
		}
		100% {
			opacity: 1;
		}
	}
	@keyframes -global-slide-out-fwd-center {
		0% {
			transform: translateZ(1);
			opacity: 1;
		}
		100% {
			transform: translateZ(600px);
			opacity: 0;
		}
	}

	@keyframes -global-from-left {
		0% {
			transform: rotateX(50deg) translateX(-200vw) skewX(-50deg);
			opacity: 1;
		}
		100% {
			transform: rotateX(0deg) translateX(0) skewX(0deg);
			opacity: 1;
		}
	}
</style>
