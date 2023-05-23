<script>
  import "./../app.css";
  import Image from './../lib/images/image.png'
  import {chosenLearner} from "../chosenLearner.js";
  import IconButton from '@smui/icon-button';

  export let learners = [
    {
      label: "Farisa",
      grade: "4th",
      baseline: {
        baseline: [80, 65, 78],
        standing: [65, 70, 75]
      },
      growth: {
        initial: [80, 65, 78],
        foxy: [80, 65, 78]
      },
      engagement: [1, 4, 3.5]
    },
    {
      label: "Alex",
      grade: "5th",
      baseline: {
        baseline: [80, 65, 78],
        standing: [90, 70, 69]
      },
      growth: {
        initial: [80, 65, 78],
        foxy: [60, 20, 60]
      },
      engagement: [4.5, 2, 3]
    }
  ]

  chosenLearner.set(learners[0]);
  export let learner;

  chosenLearner.subscribe(value => {
    learner = value;
  });
</script>


<div class="text-white flex flex-row justify-between min-h-screen">
  <div class="w-[280px] min-w-[280px] py-5 bg-[#4c6c62] px-5">

    <img src={Image} class="w-[280px]"/>

    <label>Learner</label>
    <hr class="mb-2"/>

    {#each learners as currentLearner }
      <input type="radio"
             class="ml-5"
             id={currentLearner.label}
             name="fav_language"
             checked={ currentLearner === learner }>
      <label for={currentLearner.label}
             on:click={() => chosenLearner.set(currentLearner)}>
        {currentLearner.label}
      </label>
      <br>
    {/each}

    <div class="h-12"></div>

    <label>Menu</label>
    <hr/>

    <a href="/stats" class="text-white visited:text-white block px-5 py-3 hover:bg-[#8EC6B4] cursor-pointer">Insights</a>
    <a href="/" class="text-white visited:text-white block px-5 py-3 hover:bg-[#8EC6B4] cursor-pointer">Logout</a>

  </div>
  <div class="flex-1">
    <slot />
  </div>
</div>
