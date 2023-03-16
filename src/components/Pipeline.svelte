<script>
  import StageContent from './StageContent.svelte';

  export let stages = [
    { title: 'Source' },
    { title: 'Build' },
    { title: 'Test' },
    { title: 'Deploy' },
    { title: 'Monitor' },
    { title: 'Operate' },
    { title: 'Feedback Loop' },
  ];

  let running = false;
  let activeIndex = -1;

  async function runPipeline() {
    if (running) return;
    running = true;
    for (let i = 0; i < stages.length; i++) {
      activeIndex = i;
      await new Promise(resolve => setTimeout(resolve, 5000));
    }
    activeIndex = -1;
    running = false;
  }
</script>

<style>
  .pipeline {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    position: relative;
  }
  .stage {
    flex: 1;
    min-width: 200px;
    padding: 1rem;
    background-color: #f0f0f0;
    border-radius: 10px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    position: relative;
    transition: background-color 1s ease;
  }
  .stage.running {
    background-color: #9fdf9f;
  }
  .title {
    font-weight: bold;
    margin-bottom: 0.5rem;
  }
  .connecting-line {
    position: absolute;
    top: 50%;
    left: 0;
    width: 100%;
    height: 4px;
    background-color: #333;
    z-index: -1;
  }
  .connecting-line:before,
  .connecting-line:after {
    content: '';
    position: absolute;
    width: 12px;
    height: 12px;
    background-color: #333;
    border-radius: 50%;
  }
  .connecting-line:before {
    top: -4px;
    left: -6px;
  }
  .connecting-line:after {
    top: -4px;
    right: -6px;
  }

  @keyframes spin {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }

  .loading {
    border: 2px solid #f3f3f3;
    border-top: 2px solid #3498db;
    border-radius: 50%;
    width: 16px;
    height: 16px;
    animation: spin 2s linear infinite;
    display: inline-block;
  }

</style>

<button on:click={runPipeline} disabled={running}>
  {#if !running}
    &#9658;
  {:else}
    <span class="loading"></span>
  {/if}
</button>


<div class="pipeline">
  <div class="connecting-line"></div>
  {#each stages as stage}
  <div class="stage" class:running={stage === stages[activeIndex]}>
  <div class="title">{stage.title}</div>
  <StageContent {stage} />
</div>

  {/each}
</div>
