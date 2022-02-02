<script>
    export let projectTitle;
    export let projectDescription;
    export let projectLink;
</script>

<div class="card-container">
    <div class="card-title">{projectTitle}</div>
    <hr>
    <div class="card-description">{projectDescription}</div>
    <div class="card-link">
        <button>{projectLink}</button>
    </div>
</div>

<style>
    .card-container {
        display: grid;
        overflow-x: hidden;
        grid-template-columns: auto;
        border: 2px solid white;
        border-radius: 5px;
    }

    hr{
        background-color: white !important;
        width: 100%;
        height: 1px;
    }

    .card-title {
        font-size: 24px;
        text-align: center;
    }

    .card-link,
    .card-description {
        font-size: 18px;
        margin-left: 10px;
        margin-right: 10px;
    }

    .card-description {
        margin-top: 0px;
        height: 15rem;
    }

    .card-link{
        margin-bottom: 10px;
    }

    .card-link > button {
        width: 100%;
        height: 2.5rem;
        color: white;
        font-size: 1.1rem;
        font-family: inherit;
        background-color: #828EB6;
        border-radius: 5px;
        border: none;
        cursor: pointer;
        /* do hover and click effects */
    }
</style>