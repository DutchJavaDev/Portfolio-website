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

    function gotoSlide(num){
        currentSlide = num;
    }

    let slides = [
        "one",
        "two",
        "three"
    ];

</script>

<Fullpage bind:activeSection={currentSlide}>

    <FullpageSection>
        <Landing gotoSlide={gotoSlide}/>
    </FullpageSection>

    <FullpageSection {slides} arrows>
        <!-- Create a fullpageslide per 3 projects -->
        <FullpageSlide>
            <Projects/>
        </FullpageSlide>

        <FullpageSlide>
            <Projects/>
        </FullpageSlide>

        <FullpageSlide>
            <Projects/>
        </FullpageSlide>
    </FullpageSection>

    <FullpageSection>
        <Experiences/>
    </FullpageSection>
	
    <FullpageSection>
        <About/>
    </FullpageSection>
</Fullpage>