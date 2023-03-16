<script>
  export let projects = [
    {
      title: 'Project A',
      description: 'A brief description of Project A.',
      link: 'https://example.com/project-a',
    },
    {
      title: 'Project B',
      description: 'A brief description of Project B.',
      link: 'https://example.com/project-b',
    },
  ];
</script>
<p>Replace the deployment stage with the portfolio section, highlighting the engineer's past projects. Provide a brief description, technologies used, and any relevant outcomes or achievements. Include links to live demos, source code repositories, or case studies if available.</p>
<ul>
  {#each projects as { title, description, link }}
    <li>
      <strong><a href={link} target="_blank" rel="noopener noreferrer">{title}</a></strong>
      <p>{description}</p>
    </li>
  {/each}
</ul>
