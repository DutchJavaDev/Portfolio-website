<script>
    export let gotoSlide;
    let intervalId = setInterval(changeText, 1500)
    let platforms = [
        "Web",
        "Mobile",
        "Desktop",
    ];
    let platformIndex = 0;

    function changeText(){
        if(platformIndex + 1 > platforms.length-1)
            platformIndex = 0;
        else
         platformIndex++;
    }
</script>
<div id="landing-container">
    <img src="../images/background.jpg" alt="404">
    <nav>
        <span>LOGO</span>
        <div class="nav-right">
            <span on:click={gotoSlide(1)}>Projects</span>
            <span on:click={gotoSlide(2)}>Experiences</span>
            <span on:click={gotoSlide(3)}>About me</span>
        </div>
    </nav>
    <div id="landing-message">
        <span>Hello World, my name is Boris</span>
        <br>
        <br>
        <span>I'm developer from the Netherlands</span>
        <br>
        <br>
        <span>I build applications for <span id="platform">{platforms[platformIndex]}</span> </span>
        <div id="landing-next">
            <svg on:click={gotoSlide(1)} viewBox="0 0 52 106" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M23.5251 104.447C24.892 105.814 27.108 105.814 28.4749 104.447L50.7487 82.1734C52.1156 80.8065 52.1156 78.5904 50.7487 77.2236C49.3819 75.8568 47.1658 75.8568 45.799 77.2236L26 97.0226L6.20101 77.2236C4.83418 75.8568 2.6181 75.8568 1.25126 77.2236C-0.115572 78.5904 -0.115572 80.8065 1.25126 82.1734L23.5251 104.447ZM22.5 0L22.5 101.972H29.5L29.5 0L22.5 0Z" fill="white"/>
                </svg>                
        </div>
    </div>
</div>
<style>

span {
    color: inherit;
    font-size: 28px;
}

#platform {
    color: #3575ff !important;
    font-weight: bold;
}

#landing-container {
    height: 100%;
}

#landing-message {
    margin: auto;
    width: 50%;
    margin-top: 14rem;
}

#landing-next {
    text-align: center;
}

#landing-next>svg {
    margin-top: 120px;
    width: 5%;
    height: 5%;
    cursor: pointer;
}

#landing-message>span {
    margin-left: 60px;
}

#landing-container>img {
    width: 100%;
    height: 100%;
    opacity: 10%;
    z-index: -5;
    position: absolute;
    object-fit: cover;
}

nav {
    margin-left: 5px;
}

.nav-right {
    float: right;
    margin-right: 15px;
    margin-top: 10px;
}

.nav-right>span {
    border-bottom: 3px solid white;
    padding-bottom: 5px;
    cursor: pointer;
}

.nav-right>span:hover {
    border-bottom: 3px solid gray;
    padding-bottom: 5px;
}


</style>