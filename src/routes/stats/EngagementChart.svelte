<script>
  import {ArcElement, CategoryScale, Chart as ChartJS, LinearScale} from "chart.js";
  import { Doughnut } from 'svelte-chartjs'

  ChartJS.register(
    CategoryScale, LinearScale, ArcElement
  );

  import {chosenLearner} from "../../chosenLearner.js";

  export let learner;

  chosenLearner.subscribe(value => {
    learner = value;
  });

</script>

<div class="self-center h-[500px] w-[500px]">
  <Doughnut options="{{
    plugins: {
      title: {
          display: true,
          text: ''
      }
    }
  }}" data={{
  labels: [
    'Math',
    'English',
    'Biology'
  ],
  datasets: [{
    label: learner.label,
    data: learner.engagement,
    backgroundColor: [
      'rgb(255, 99, 132)',
      'rgb(54, 162, 235)',
      'rgb(255, 205, 86)'
    ],
    hoverOffset: 4
  }]
}}/>
</div>
<style>
</style>