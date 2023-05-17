<script lang="ts">
  import { goto } from '$app/navigation';
  import { fly } from 'svelte/transition';

  let email = "";

  function isValidEmail(email: string): boolean {
    const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return regex.test(email);
  }

  function submitForm() {
    console.log(email);
    goto("/programs/success", { transition: fly });
  }
</script>

<main class="bg-black h-screen w-screen flex items-center justify-center">
  <div in:fly="{{ duration: 300 }}" out:fly="{{ duration: 300 }}" class="w-card px-12 py-8 flex flex-col items-center justify-center text-center text-xl bg-white rounded-lg shadow-lg">
    <p class="my-auto">
      Once we receive your email, we'll finalize your subscription and provide you with all the necessary details to get started on your empowering fitness journey.
    </p>

    <div class="input-wrapper my-auto">
      <input
        type="email"
        placeholder="Enter your email"
        class="mt-1 w-full px-3 py-2 border border-black rounded"
        bind:value={email}
      />

      <button
        class={`mt-4 px-4 transition-all font-bold hover:bg-green-600 text-xl py-2 rounded ${isValidEmail(email) ? 'bg-green-500 text-white' : 'bg-green-500 opacity-50 text-white'}`}
        disabled={!isValidEmail(email)}
        on:click={submitForm}
      >
        Submit
      </button>
    </div>
  </div>
</main>

<style>
    .w-card{
    width: 50vh;
    min-height: 520px;

}
main{
    background-attachment: fixed;
      background-image: url("static/empty.avif") ;
      background-repeat: no-repeat;
      background-size: cover;
      background-position: center;
  }
</style>
