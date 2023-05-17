<script lang="ts">
    import { fly } from 'svelte/transition';
    import { onMount } from 'svelte';

    onMount(() => {
        setTimeout(() => {
            window.location.href = '/';
        }, 3000); // Redirect after 3 seconds (adjust as needed)
    });
</script>

<main class="bg-black h-screen w-screen flex items-center justify-center">
    <div in:fly="{{ duration: 300 }}" out:fly="{{ duration: 300 }}" class="w-card px-12 py-8 flex flex-col items-center justify-center text-center text-xl bg-white rounded-lg shadow-lg">
        <p class="my-auto">
            done!!! you will be shortly redirected to the main page :3
        </p>
    </div>
</main>
<style>
    .w-card{
        width: 50vh;
        min-height: 520px;
    
    }
    main{
        background-attachment: fixed;
          background-image: url("images/empty.avif") ;
          background-repeat: no-repeat;
          background-size: cover;
          background-position: center;
      }
    </style>