<script>
    import Card from "./Card.svelte";
    import ClassData from "$lib/ClassData.json";
    import CoopData from "$lib/CoopData.json"
    import PieChart from "$lib/PieChart.svelte";
</script>

<Card>
    <h2>
        Degree Progress
    </h2>

    <div class = "charts">
        <PieChart data = {ClassData} />
        <PieChart data = {CoopData} />
    </div>

    <div class = "key">
        <div class = listItem>
            <div class = "keyElipse" style="background-color:#25EC93"></div>
            <text> complete </text>
            <button> Details Placeholder </button>
        </div>
        <div class = listItem>
            <div class = "keyElipse" style="background-color:#EC2542"></div> 
            <text> missing </text>
            <button> Details Placeholder </button>
        </div>
        <div class = listItem>
            <div class = "keyElipse" style="background-color:#6CC6EA"></div>
            <text> in progress </text>
            <button> Details Placeholder </button>
        </div>
        <div class = listItem>
            <div class = "keyElipse" style="background-color:#F3F3F3"></div>
            <text> future </text>
            <button> Details Placeholder </button>
        </div>
    </div>
</Card>

<style>

    .charts{
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 20px;
        align-self: stretch;
    }

    .key{
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        align-self: stretch;
    }

    .listItem{
        display: flex;
        padding: 5px 10px;
        align-items: center;
        gap: 10px;
        align-self: stretch;
        justify-content: space-between;
    }

    .keyElipse{
        width: 24px;
        height: 24px;
        aspect-ratio: 1/1;
        stroke-width: 1px;
        border-radius: 12px;
    }
</style>