<script>
  export let jobs = [
    {
      title: 'DevOps Engineer',
      company: 'Company A',
      duration: '2021 - Present',
    },
    {
      title: 'System Administrator',
      company: 'Company B',
      duration: '2019 - 2021',
    },
  ];
</script>
<p>Showcase the engineer's work experience, including the companies they've worked for, their roles, and the duration of employment. Use the test stage to illustrate how they've applied their skills in real-world scenarios and their ability to adapt to new tools and technologies.</p>
<ul>
  {#each jobs as { title, company, duration }}
    <li>
      <strong>{title}</strong> at {company} ({duration})
    </li>
  {/each}
</ul>
