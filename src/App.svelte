<script>
    //Svelte import
    import { 
        Fullpage,
        FullpageSection,
        FullpageSlide
    } from 'svelte-fullpage';
    //Optional, include all titles of your sections, this is also used as number that indicate count of sections
    const sections = [
        'Landing',
        'Projects',
        'Experiences',
        'About me'
    ];

	// Project slides
    const slides = [
        'one',
        'two',
        'three'
    ];
</script>

<Fullpage {sections} arrows>

    <FullpageSection center>
        Landing
    </FullpageSection>

    <FullpageSection {slides} arrows>
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