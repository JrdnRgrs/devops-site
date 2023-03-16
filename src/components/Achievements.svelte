<script>
  export let achievements = [
    {
      title: 'Certified Kubernetes Administrator',
      year: 2021,
    },
    {
      title: 'AWS Certified DevOps Engineer',
      year: 2020,
    },
  ];
</script>
<p>In the operation stage, list any significant achievements or awards the engineer has received throughout their career. Include client or coworker testimonials that speak to their expertise and skills.</p>
<ul>
  {#each achievements as { title, year }}
    <li>
      {title} ({year})
    </li>
  {/each}
</ul>
