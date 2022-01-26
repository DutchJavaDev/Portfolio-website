<script>
    // load from gihub or api..
    import ProjectCard from './ProjectCard.svelte';
    import { onMount } from 'svelte';

    onMount(() => {

    });

    function mouseleave(e) {
        console.log(e);
    }

    let projects = [
        {
            title:"Project title",
            description:"Project description",
            link:"View on github",
        },
        {
            title:"Project title",
            description:"Project description",
            link:"View on github",
        },
        {
            title:"Project title",
            description:"Project description",
            link:"View on github",
        }
    ];
</script>
    <div class="project-title">Projects</div>
    <div class="project-container" on:mouseleave={mouseleave}>
        {#each projects as project}
        <ProjectCard projectTitle={project.title} projectDescription={project.description} projectLink={project.link} />
        {/each}
    </div>
<style>
.project-title {
    text-align: center;
    font-size: 2.5rem;
}

.project-container {
    overflow-y: auto;
    display: grid;
    grid-column-gap: 10rem;
    grid-row-gap: 2rem;
    margin-top: 12.5%;
    margin-left: 5rem;
    margin-right: 5rem;
    grid-template-columns: auto auto auto;
}
</style>