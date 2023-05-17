<script>
    import { onMount } from 'svelte';
    import Saos from "/node_modules/saos";
</script>

<main class="h-screen flex items-center justify-center">
    
    <div class="bg-transparent text-black flex flex-col items-center justify-center text-semibold text-2xl rounded-lg p-6 mx-auto w-6/12 my-4">
        <Saos
				animation={'fade-in 1.2s cubic-bezier(0.390, 0.575, 0.565, 1.000) both'}
				animation_out={'slide-out-fwd-center 0.7s cubic-bezier(0.550, 0.085, 0.680, 0.530) both'}
				top={250}
				bottom={250}
			>
      <p class="text-white text-center text-bold text-2xl rounded-lg p-6 mx-auto w-6/12 my-4">
        Join us at GymForce and unlock your full potential
      </p>
    </Saos>
    <Saos
    animation={'fade-in 1.2s cubic-bezier(0.390, 0.575, 0.565, 1.000) both'}
    animation_out={'slide-out-fwd-center 0.7s cubic-bezier(0.550, 0.085, 0.680, 0.530) both'}
    top={250}
    bottom={250}
>
      <a href="/programs" class="bg-white hover:bg-green-500 text-black transition-colors font-bold  p-8 rounded">
        Start your journey
      </a>
    </Saos>

    </div>

  </main>
  <style>
    main {
    height: 100vh;
    background-attachment: fixed;
    background-image: url('https://drive.google.com/uc?export=view&id=1IcgMVLiYdp8jsAtYf5LhEoEY8K_pat3e');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: bottom;
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

</style>