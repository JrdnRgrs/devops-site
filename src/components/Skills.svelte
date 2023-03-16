<script>
  export let skills = [
    "Docker",
    "Kubernetes",
    "Jenkins",
    "Terraform",
    "Python",
    "AWS",
    "Azure",
    "Git",
  ];
</script>

<style>
  ul {
    display: flex;
    flex-wrap: wrap;
    list-style-type: none;
    padding: 0;
    gap: 0.5rem;
  }
  li {
    background-color: #4caf50;
    color: white;
    padding: 0.25rem 0.5rem;
    border-radius: 5px;
  }
</style>
<p> In this stage, list the engineer's core skills, programming languages, tools, and technologies they're proficient in. Also, include relevant certifications and any additional training they've completed.</p>
<ul>
  {#each skills as skill}
    <li>{skill}</li>
  {/each}
</ul>
