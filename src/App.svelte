<script>
    //Svelte import
    import { 
        Fullpage,
        FullpageSection,
        FullpageSlide
    } from 'svelte-fullpage';

    import Landing from './Components/Landing.svelte';
    import Projects from './Components/Projects.svelte';
    import Experiences from './Components/Experience.svelte';
    import About from './Components/About.svelte';

    let currentSlide = 0;
    let projectsPerSlide = 3;

    function gotoSlide(num){
        currentSlide = num;
    }

    let slides = [];


    // Dummy projects
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
        },
        {
            title:"Project title",
            description:"Project description",
            link:"View on github",
        }
    ];

    let projectSetPer3 = [];

    let temp = [];

    for (let i = 0; i < projects.length; i++)
    {
        temp.push(projects[i]);
        if(temp.length % projectsPerSlide == 0)
        {
            projectSetPer3.push(temp);
            temp = [];
            slides.push(i*i);
        }
        else if(i == projects.length-1)
        {
            projectSetPer3.push(temp);
            temp = [];
            slides.push(i*i);
        }
    }
</script>

<Fullpage bind:activeSection={currentSlide}>

    <FullpageSection>
        <Landing gotoSlide={gotoSlide}/>
    </FullpageSection>

    <FullpageSection {slides} arrows>
        {#each projectSetPer3 as projectSet}
            <FullpageSlide>
                <Projects projects={projectSet}/>
            </FullpageSlide>
        {/each}
    </FullpageSection>

    <FullpageSection>
        <Experiences/>
    </FullpageSection>
	
    <FullpageSection>
        <About/>
    </FullpageSection>
</Fullpage>