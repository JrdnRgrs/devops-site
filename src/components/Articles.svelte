<script>
  export let articles = [
    {
      title: 'Article A',
      link: 'https://example.com/article-a',
    },
    {
      title: 'Article B',
      link: 'https://example.com/article-b',
    },
  ];
</script>
<p>The monitoring stage can represent the engineer's thoughts and insights on industry trends and best practices. Use this section to display blog posts or articles they've written, sharing their knowledge and experiences in DevOps.</p>
<ul>
  {#each articles as { title, link }}
    <li>
      <a href={link} target="_blank" rel="noopener noreferrer">{title}</a>
    </li>
  {/each}
</ul>
