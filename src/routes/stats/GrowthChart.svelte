<script>
  import {BarElement, CategoryScale, Chart as ChartJS, LinearScale, Title,} from "chart.js";
  import {Bar} from 'svelte-chartjs'

  ChartJS.register(
    CategoryScale,
      LinearScale,
      BarElement,
      Title
  );

  import {chosenLearner} from "../../chosenLearner.js";

  export let learner;

  chosenLearner.subscribe(value => {
    learner = value;
  });

</script>

<div class="self-center h-[600px] w-[800px]">
  <Bar options="{{
    plugins: {
      title: {
          display: true,
          text: ''
      }
    },
    indexAxis: 'y',
    scales: {
      x: {
        stacked: true,
      },
      y: {
        stacked: true
      }
    }
  }}" data={{
  labels: [
    'Math',
    'English',
    'Biology'
  ],
  datasets: [{
    label: 'School',
    data: learner.growth.initial,
    backgroundColor: '#B07264',
  }, {
    label: 'Foxy',
    data: learner.growth.foxy,
    backgroundColor: '#8EC6B4'
  }]
}}/>
</div>
<style>
</style>