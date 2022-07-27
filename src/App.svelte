<script>
    //Svelte import
    import { onMount } from 'svelte';
    import { 
        Fullpage,
        FullpageSection,
        FullpageSlide
    } from 'svelte-fullpage';

    import Landing from './Components/Landing.svelte';
    import Projects from './Components/Projects.svelte';
    import Experience from './Components/Experience.svelte';
    import About from './Components/About.svelte';
    import api from 'api.js';

    let currentSlide = 0;
    let projectsPerSlide = 3;

    function gotoSlide(num){
        currentSlide = num;
    }

    onMount(async () => {
		const all = api.all();
	});

    let projectSlides = [];
    let experienceSlides = [];

    // Dummy experiences
    let experience = [
        {
            year: "2000 - 2001 @ Appec",
            title: "Fullstack developer",
            description: "Project description, Project description, Project description,Project description",
            stack: "C#, ASP.NET MVC"
        },
        {
            year: "2000 - 2001 @ Appec",
            title: "Fullstack developer",
            description: "Project description, Project description, Project description,Project description",
            stack: "C#, ASP.NET MVC"
        },
        {
            year: "2000 - 2001 @ Appec",
            title: "Fullstack developer",
            description: "Project description, Project description, Project description,Project description",
            stack: "C#, ASP.NET MVC"
        },
        {
            year: "2000 - 2001 @ Appec",
            title: "Fullstack developer",
            description: "Project description, Project description, Project description,Project description",
            stack: "C#, ASP.NET MVC"
        },
    ];

    let experiencesSetPer3 = [];

    let temp = [];

    for (let i = 0; i < experience.length; i++)
    {
        temp.push(experience[i]);
        if(temp.length % projectsPerSlide == 0)
        {
            experiencesSetPer3.push(temp);
            temp = [];
            experienceSlides.push(i*i);
        }
        else if(i == experience.length-1)
        {
            experiencesSetPer3.push(temp);
            temp = [];
            experienceSlides.push(i*i);
        }
    }


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

    temp = [];

    for (let i = 0; i < projects.length; i++)
    {
        temp.push(projects[i]);
        if(temp.length % projectsPerSlide == 0)
        {
            projectSetPer3.push(temp);
            temp = [];
            projectSlides.push(i*i);
        }
        else if(i == projects.length-1)
        {
            projectSetPer3.push(temp);
            temp = [];
            projectSlides.push(i*i);
        }
    }
</script>

<Fullpage bind:activeSection={currentSlide}>

    <FullpageSection>
        <Landing gotoSlide={gotoSlide}/>
    </FullpageSection>

    <FullpageSection slides={projectSlides}>
        {#each projectSetPer3 as projectSet}
            <FullpageSlide>
                <Projects projects={projectSet}/>
            </FullpageSlide>
        {/each}
    </FullpageSection>

    <FullpageSection slides={experienceSlides}>
       {#each experiencesSetPer3 as experienceSet}
        <FullpageSlide>
            <Experience experiences={experienceSet} />
        </FullpageSlide>
       {/each}
    </FullpageSection>
	
    <FullpageSection>
        <About/>
    </FullpageSection>
</Fullpage>