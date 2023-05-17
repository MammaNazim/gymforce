<!-- Component2.svelte -->
<script>
  import { onMount } from 'svelte';
  import Saos from "/node_modules/saos";
  
  let images = [
    "https://drive.google.com/uc?export=view&id=1QKdL8P0p_rVOU8ZFLoNguAq2jQTAohAp",
    "https://drive.google.com/uc?export=view&id=1Sym5V3q1bm4ui_VExsDJB5cxjFl-_CIE",
    "https://drive.google.com/uc?export=view&id=1c7rRCRYl0aSnH1fSmKSQ0yckQKGoZygq",
    "https://drive.google.com/uc?export=view&id=1ukcQmBkEWwUxwd2CQORW5Sb3fja00ycM",
    "https://drive.google.com/uc?export=view&id=1--UGrfInHL-DEYM6Olm11THo08imHah2",
    "https://drive.google.com/uc?export=view&id=1JH1qg4N0sOR7Pa7-10gE1MM6b75sJrTz",


  ];
  let images2 = [
    "https://drive.google.com/uc?export=view&id=1i6ZFdsyoiMrNIubGQegnTHaU39gXpdde",
    "https://drive.google.com/uc?export=view&id=1yDU5qzRHcAow76UyhYdtlFuad-ThqVTh"

  ]
  onMount(() => {

  });
  </script>
  
<main class=" flex flex-col justify-center content-center h-screen bg-black ">
  <Saos animation={'slide-in-left 1s cubic-bezier(0.35, 0.5, 0.65, 0.95) both'}>
    <div class="container mx-auto py-8">
      <div class="bg-transparent flex">
        <div class="basis-2/4 py-4 pr-52">
          <p class="text-white text-lg">
            Our state-of-the-art facility is equipped with top-of-the-line fitness equipment, carefully selected to cater to a wide range of workouts and training styles. Whether you're a seasoned athlete looking to push your limits, a beginner starting your fitness journey, or someone in between, our gym offers a diverse range of equipment and amenities to accommodate all levels of fitness enthusiasts.
          </p>
        </div>
        <div class="basis-2/4">
          <div class="bg-transparent grid grid-cols-6 grid-rows-1 gap-4">
            {#each images as image, index}
              <div class="relative aspect-w-1 aspect-h-1">
                <img src={image} alt="gym" class="object-cover w-full h-full">
                <div class="absolute bottom-0 left-0 p-2 bg-black bg-opacity-50 text-white">
                </div>
              </div>
            {/each}
          </div>
        </div>
      </div>
    </div>
  </Saos>

  <Saos animation={'slide-in-right 1s cubic-bezier(0.35, 0.5, 0.65, 0.95) both'}>
    <div class="container mx-auto py-8">
      <div class="bg-transparent flex items-center">
        <div class="grid grid-cols-2 grid-rows-1 pr-52 gap-4">
          {#each images2 as image, index}
              <div class="relative aspect-w-1 aspect-h-1">
                <img src={image} alt="gym" class="object-cover mx-auto w-full h-full">
                <div class="absolute bottom-0 left-0 p-2 bg-black bg-opacity-50 text-white">
                </div>
              </div>
            {/each}
        </div>
        <div class=" py-4 ">
          <p class=" text-white text-lg  h-full">
            At GymForce, we believe that fitness should be an enjoyable and inclusive experience. Our vibrant and energetic atmosphere creates a positive and welcoming community where individuals of all backgrounds and fitness levels can thrive. Whether you prefer high-intensity group classes, one-on-one training sessions, or simply working out at your own pace, you'll find a range of options to suit your preferences.
          </p>
        </div>
      </div>
    </div>
  </Saos>
  <div class="flex text-white justify-center mt-4">
    <a href="#about3" class="">
      <svg
        class="w-16 h-16 transition-all duration-300 cursor-pointer rounded-full  hover:opacity-80 animate-pulse transform hover:scale-125"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"/>
      </svg>
    </a>
  </div>
</main>


<style>
  @keyframes -global-slide-in-left {
  0% {
    transform: translateX(-1000px);
    opacity: 0;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}
@keyframes -global-slide-in-left {
  0% {
    transform: translateX(-1000px);
    opacity: 0;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}
  @keyframes -global-slide-in-right {
  0% {
    transform: translateX(1000px);
    opacity: 0;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}


  </style>