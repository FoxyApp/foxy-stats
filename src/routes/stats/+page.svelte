<script>
  import BaselineChart from "./BaselineChart.svelte";
  import GrowthChart from "./GrowthChart.svelte";
  import EngagementChart from "./EngagementChart.svelte";

  import {chosenLearner} from "../../chosenLearner.js";

  export let learner;

  chosenLearner.subscribe(value => {
      learner = value;
  });

  import Tab, { Icon, Label } from '@smui/tab';
  import TabBar from '@smui/tab-bar';

  let tabs = [
      {
          icon: 'timer',
          label: 'Engagement',
      },
      {
          icon: 'rocket_launch',
          label: 'Growth',
      },
      {
          icon: 'diversity_3',
          label: 'Peers',
      },
  ];
  let active = tabs[0];
</script>

<svelte:head>
    <title>Foxy Insights - {learner.label}</title>
</svelte:head>

<h1 class="text-2xl text-black font-bold m-4">Insights for {learner.label} - {learner.grade} grade</h1>

<TabBar {tabs} let:tab bind:active class="mb-5">
    <Tab {tab}>
        <Icon class="material-icons">{tab.icon}</Icon>
        <Label>{tab.label}</Label>
    </Tab>
</TabBar>

{#if active.label === 'Engagement'}
    <EngagementChart />
{:else if active.label === 'Growth'}
    <GrowthChart />
{:else if active.label === 'Peers'}
    <BaselineChart />
{/if}

