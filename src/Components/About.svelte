<script>
  function openLinkedIn() {
    openTab("https://www.linkedin.com/in/boris-mulder-473987153/");
  }

  function openGithub() {
    openTab("https://github.com/DutchJavaDev");
  }

  function openTab(url) {
    window.open(url, "_blank").focus();
  }
</script>

<div class="about-title">About me</div>

<div class="about-container">
<span>My name is Boris and I live in the netherlands.</span>
<br>
<br>
<span>Programming started out as hobby for me when I was a teenager, I did not think to do much with it until I was older when I was thinking of what i wanted to become when i grow up.
</span>
<br>
<br>
<span>I decided I wanted to turn my hobby in to my job, fast forward and I am now doing a ICT course at Fontys University in Eindhoven.
</span>
</div>

<footer>
  <img src="../images/background.jpg" alt="404" />
  <div class="socials">
    <i on:click={openLinkedIn} class="fab fa-linkedin fa-3x" />
    <i on:click={openGithub} class="fab fa-github fa-3x" />
  </div>
</footer>

<style>
  .about-title {
    text-align: center;
    font-size: 2.5rem;
    margin-bottom: 3rem;
  }

  .about-container{
      margin: 0px auto;
      width: 35%;
      height: 75%;
      font-size: 1.2rem;
  }

  footer {
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 10%;
  }

  .socials {
    display: grid;
    grid-template-columns: 5rem 5rem;
    justify-content: center;
  }

  .socials > i {
    margin-top: 20px;
    cursor: pointer;
  }

  footer > img {
    width: 100%;
    height: 100%;
    opacity: 10%;
    z-index: -5;
    position: absolute;
    object-fit: cover;
  }
</style>
