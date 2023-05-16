<script lang="ts">
	import { createEventDispatcher} from 'svelte';
	import { fade } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	let weight: any = 40;
	let height: any = 100;
	let bmiResult: any = false;
	let goals = ['fat loss', 'muscle gain', 'fitness and wellbeing'];
	let selectedGoal = '';
	let selectedNumber: number;
  
	const dispatch = createEventDispatcher();
  
	function calculateBMI() {
	  if (weight && height) {
		const weightInKg = parseFloat(weight);
		const heightInM = parseFloat(height) / 100; // Convert height from cm to meters
		const bmi = weightInKg / (heightInM * heightInM);
		bmiResult = bmi.toFixed(2);
	  } else {
		bmiResult = '';
	  }
	}
  
	$: {
	  const isButtonDisabled = !(weight && height && selectedGoal && selectedNumber);
	  dispatch('buttonState', { disabled: isButtonDisabled });
	}
  </script>

<main  class="bg-black h-screen w-screen flex items-center justify-center">
	{#if !bmiResult}
		<div in:fade="{{delay: 0, duration: 500, easing: quintOut}}" class="w-card  w-3/6  px-12 py-8 bg-white rounded-lg shadow-lg  "> 
			<h1 class="text-3xl">Take our test</h1>
			<div>
				<div  class="w-full mb-4">
					<label for="weight" class="block text-lg mb-2 text-black">Weight (kg):</label>
					<input
						type="number"
						id="weight"
						class="w-full px-3 py-2 border border-black rounded"
						bind:value={weight}
						min="40"
						max="250"
					/>
					{#if weight > 250}
						<p class="text-red-500">Weight should not exceed 250 kg.</p>
					{/if}
					{#if weight < 40}
					<p class="text-red-500">Weight should not be less than 40 kg.</p>
				{/if}
				</div>
				<div class="w-full mb-4">
					<label for="height" class="block text-lg mb-2 text-black">Height (cm):</label>
					<input
						type="number"
						id="height"
						class="w-full px-3 py-2 border border-black rounded"
						bind:value={height}
						min="100"
						max="250"
					/>
					{#if height > 250}
						<p class="text-red-500">Height should not exceed 250 cm.</p>
					{/if}
					{#if height < 100}
					<p class="text-red-500">Height should not be less than 100 cm.</p>
				{/if}
				</div>
				<label class="text-lg">What's your goal?</label>
				<div class="flex flex-col">
					{#each goals as goal}
						<label>
							<input type="radio" bind:group={selectedGoal} value={goal} />
							{goal}
						</label>
					{/each}
				</div>
				<div>
					<label class="text-lg" for="numbers">Days of training per week:</label>
					<div class="flex flex-row justify-evenly" id="numbers">
						{#each Array.from({ length: 7 }, (_, i) => i + 1) as number}
							<label class="">
								<input type="radio" bind:group={selectedNumber} value={number} />
								<div>{number}</div>
							</label>
						{/each}
					</div>
				</div>
				<div class="flex justify-center">
					<button
						class="mt-4 py-2 px-4 bg-green-500 text-white rounded disabled:opacity-50"
						on:click={calculateBMI}
						disabled={!(weight && height && selectedGoal && selectedNumber)}
					>
						Next
					</button>
				</div>
			</div>
		</div>
	{:else if bmiResult }
	<div  class="w-card px-12 py-8 flex flex-col items-center justify-center text-center text-xl bg-white rounded-lg shadow-lg">
            
			{#if selectedNumber >= 2}
				<p  in:fade="{{delay: 0, duration: 500, easing: quintOut}}" class=" my-auto">
					your BMI is {bmiResult}. your goal is {selectedGoal} and you're willing to train {selectedNumber}
					days a week
				</p>
			{:else}
				<p  in:fade="{{delay: 0, duration: 500, easing: quintOut}}" class=" my-auto">
					your BMI is {bmiResult}. your goal is {selectedGoal} and you're willing to train once a week
				</p>
			{/if}
			<a href="/programs/email" in:fade="{{delay: 0, duration: 500, easing: quintOut}}"  class="bg-green-500 hover:bg-green-600 text-white my-auto  font-bold py-2 px-4 rounded">
				Show results
			</a>
		</div>
		

	{/if}
</main>

<style>
.w-card{
    width: 50vh;
    min-height: 520px;

}
main{
    background-attachment: fixed;
      background-image: url("src/images/empty.avif") ;
      background-repeat: no-repeat;
      background-size: cover;
      background-position: center;
  }
</style>