<script>
  import {
    Chart as ChartJS,
    Filler,
    Legend,
    LineElement,
    PointElement,
    RadialLinearScale,
    Title,
    Tooltip,
  } from "chart.js";
  import {Radar} from 'svelte-chartjs'

  ChartJS.register(
      Title,
      Tooltip,
      Legend,
      RadialLinearScale,
      PointElement,
      LineElement,
      Filler,
      Title
  );


  import {chosenLearner} from "../../chosenLearner.js";

  export let learner;

  chosenLearner.subscribe(value => {
    learner = value;
  });
</script>

<div class="w-full self-center">
  <Radar options="{{
      plugins: {
        title: {
            display: true,
            text: ''
        }
      },
      scales: {
        r: {
            beginAtZero: true
        }
    },
  }}" data={{
  labels: [
    'Math',
    'English',
    'Biology'
  ],
  datasets: [{
    label: learner.label,
    data: learner.baseline.standing,
    fill: true,
    backgroundColor: '#8EC6B423',
    borderColor: '#8EC6B4',
    pointBackgroundColor: '#8EC6B423',
    pointBorderColor: '#fff',
    pointHoverBackgroundColor: '#fff',
    pointHoverBorderColor: '#8EC6B4'
  }, {
    label: 'Baseline of other ' + learner.grade + ' graders',
    data: learner.baseline.baseline,
    fill: true,
    backgroundColor: '#B4977123',
    borderColor: '#B49771',
    pointBackgroundColor: '#B4977123',
    pointBorderColor: '#fff',
    pointHoverBackgroundColor: '#fff',
    pointHoverBorderColor: '#B4977123'
  }]
}}/>
</div>
<style>
</style>