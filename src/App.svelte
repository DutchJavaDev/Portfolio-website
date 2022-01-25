<script>
    //Svelte import
    import { 
        Fullpage,
        FullpageSection,
        FullpageSlide
    } from 'svelte-fullpage';

    import Landing from './Components/Landing.svelte';

    //Optional, include all titles of your sections, this is also used as number that indicate count of sections
    // const sections = [
    //     'Landing',
    //     'Projects',
    //     'Experiences',
    //     'About me'
    // ];

	// Project slides
    // const slides = [
    //     'one',
    //     'two',
    //     'three'
    // ];

    let currentSlide = 0;

    function setSlide(num){
        currentSlide = num;
    }

</script>

<Fullpage arrows bind:activeSection={currentSlide}>

    <FullpageSection>
        <Landing gotoSlide={setSlide}/>
    </FullpageSection>

    <FullpageSection arrows>
        <FullpageSlide>
            Projects#
        </FullpageSlide>
        <FullpageSlide>
            Projects#
        </FullpageSlide>
        <FullpageSlide>
            Projects#
        </FullpageSlide>
    </FullpageSection>

    <FullpageSection>
        Experiences
    </FullpageSection>
	
    <FullpageSection>
        About me
    </FullpageSection>
</Fullpage>