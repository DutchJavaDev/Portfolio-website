<script>
    // load from gihub or api..
    import ProjectCard from './ProjectCard.svelte';

    export let projects;

</script>
    <div class="project-title">Projects</div>
    <div class="project-container">
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
    grid-column-gap: 5rem;
    margin-top: 12.5%;
    margin-left: 5rem;
    margin-right: 5rem;
    grid-template-columns: 1fr 1fr 1fr;
}
</style>