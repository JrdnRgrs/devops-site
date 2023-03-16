<script>
  import Education from './Education.svelte';
  import Skills from './Skills.svelte';
  import Experience from './Experience.svelte';
  import Portfolio from './Portfolio.svelte';
  import Articles from './Articles.svelte';
  import Achievements from './Achievements.svelte';
  import Contact from './Contact.svelte';

  export let stage = null;
  let Component = null;

  $: {
    if (stage) {
      switch (stage.title) {
        case 'Source':
          Component = Education;
          break;
        case 'Build':
          Component = Skills;
          break;
        case 'Test':
          Component = Experience;
          break;
        case 'Deploy':
          Component = Portfolio;
          break;
        case 'Monitor':
          Component = Articles;
          break;
        case 'Operate':
          Component = Achievements;
          break;
        case 'Feedback Loop':
          Component = Contact;
          break;
        default:
          Component = null;
      }
    }
  }
</script>

{#if Component}
  <svelte:component this={Component} />
{/if}
