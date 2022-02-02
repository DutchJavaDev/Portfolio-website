<script>
  import ExperienceCard from './ExperienceCard.svelte'
  export let experiences;

</script>
<div class="experience-title">Experiences</div>
<div class="experience-container">
  {#each experiences as exp}
  <ExperienceCard experienceYear={exp.year} experienceTitle={exp.title} experienceDescription={exp.description}/>
{/each}
</div>

<style>
  .experience-title {
    font-size: 2.5rem;
    text-align: center;
  }
  .experience-container {
    overflow-y: auto;
    display: grid;
    grid-column-gap: 5rem;
    margin-top: 12.5%;
    margin-left: 5rem;
    margin-right: 5rem;
    grid-template-columns: 1fr 1fr 1fr;
  }
</style>
