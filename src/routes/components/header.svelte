<!-- Header.svelte -->
<script lang="ts">
  import { onMount } from 'svelte';

  onMount(() => {
    // Add any necessary JavaScript logic for the header component
  });
</script>

<header class=" z-50 fixed w-screen bg-black py-4 px-6">
  <div class="container mx-auto flex justify-between items-center">
    <a href="/" class="flex items-center ">
      <img src="https://drive.google.com/uc?export=view&id=1_p-Gzx53J8MrquvmcOHqB7fmRvgGvXMu" alt="Barbell Logo" class=" h-6 mr-2" />
      <h1 class="text-white text-2xl font-bold uppercase transition-colors duration-300">GYMFORCE</h1>
    </a>

    <nav class="space-x-4">
      <a href="/#about1" class="text-white  font-semibold transition-colors duration-300 text-lg bg-transparent hover:bg-green-500 hover:text-white py-2 px-4 rounded-full">About</a>
      <a href="/programs" class="text-white font-semibold transition-colors duration-300 text-lg bg-transparent hover:bg-green-500 hover:text-white py-2 px-4 rounded-full">Programs</a>
      <a href="/contact" class="text-white font-semibold transition-colors duration-300 text-lg bg-transparent hover:bg-green-500 hover:text-white py-2 px-4 rounded-full">Coaching</a>
    </nav>
  </div>
</header>
