<script>
  import {BarElement, CategoryScale, Chart as ChartJS, LinearScale,} from "chart.js";
  import {Bar} from 'svelte-chartjs'

  ChartJS.register(
    CategoryScale,
      LinearScale,
      BarElement
  );
</script>
<div class="">
  <Bar options="{{
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
    'Terme mit Variablen',
    'Geometrie',
    'Lineare Gleichungen',
    'Kenngrößen von Daten',
    'Kongruenz'
  ],
  datasets: [{
    label: 'School',
    data: [65, 70, 75, 90, 85, 95, 95],
    backgroundColor: '#B07264',
  }, {
    label: 'Foxy',
    data: [80, 65, 78, 80, 60, 95, 85],
    backgroundColor: '#8EC6B4'
  }]
}}/>
</div>
<style>
</style>