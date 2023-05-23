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
    backgroundColor: 'rgba(255, 99, 132, 0.2)',
    borderColor: 'rgb(255, 99, 132)',
    pointBackgroundColor: 'rgb(255, 99, 132)',
    pointBorderColor: '#fff',
    pointHoverBackgroundColor: '#fff',
    pointHoverBorderColor: 'rgb(255, 99, 132)'
  }, {
    label: 'Baseline',
    data: [80, 65, 78, 80, 60],
    fill: true,
    backgroundColor: 'rgba(212, 175, 55, 0.2)',
    borderColor: 'rgba(212, 175, 55, 0.7)',
    borderDash: [9, 4, 3, 4],
    pointBackgroundColor: 'rgb(212, 175, 55)',
    pointBorderColor: '#fff',
    pointHoverBackgroundColor: '#fff',
    pointHoverBorderColor: 'rgb(212, 175, 55)'
  }]
}}/>
</div>
<style>
</style>