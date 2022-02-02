<script>
    export let experienceYear;
    export let experienceTitle;
    export let experienceDescription;
</script>

<div class="card-container">
    <div class="card-year">{experienceYear}</div>
    <br>
    <br>
    <div class="card-title">{experienceTitle}</div>
    <br>
    <div class="card-description">{experienceDescription}</div>
</div>

<style>
    .card-container {
        display: grid;
        grid-template-columns: auto;
        border: 2px solid white;
        border-radius: 5px;
    }

    .card-title, .card-year {
        font-size: 22px;
        text-align: left;
        margin-left: 10px;
        margin-right: 10px;
    }

    .card-year {
        margin-top: 2px;
        font-size: 24px;
    }

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
</style>
