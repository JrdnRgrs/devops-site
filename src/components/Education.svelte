<script>
  export let education = [
    {
      degree: "Bachelor of Science in Computer Science",
      institution: "XYZ University",
      year: "2018 - 2022",
    },
    {
      degree: "AWS Certified DevOps Engineer",
      institution: "Amazon Web Services",
      year: "2022",
    },
  ];
</script>

<style>
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    margin-bottom: 0.5rem;
  }
</style>
<p>the source stage represents the DevOps engineer's education history. Display the degree(s) obtained, institution names, and graduation dates.</p>
<ul>
  {#each education as { degree, institution, year }}
    <li>
      <strong>{degree}</strong> <br />
      {institution} <br />
      {year}
    </li>
  {/each}
</ul>
