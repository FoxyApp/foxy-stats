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
      Filler
  );
</script>
<div class="">
  <Radar options="{{
      scales: {
        r: {
            beginAtZero: true
        }
    },
  }}" data={{
  labels: [
    'Terme mit Variablen',
    'Geometrie',
    'Lineare Gleichungen',
    'Kenngrößen von Daten',
    'Kongruenz'
  ],
  datasets: [{
    label: 'Farisa',
    data: [65, 70, 75, 90, 85],
    fill: true,
    backgroundColor: '#8EC6B423',
    borderColor: '#8EC6B4',
    pointBackgroundColor: '#8EC6B423',
    pointBorderColor: '#fff',
    pointHoverBackgroundColor: '#fff',
    pointHoverBorderColor: '#8EC6B4'
  }, {
    label: 'Baseline',
    data: [80, 65, 78, 80, 60],
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