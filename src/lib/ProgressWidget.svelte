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
        <div class = "pieChart">
            <PieChart data = {ClassData} />
            <text>Classes</text>
        </div>
        <div class = "pieChart">
            <PieChart data = {CoopData} />
            <text>Co-op</text>
        </div>
    </div>

    <div class = listContainer>
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

    .pieChart{
        display: flex;
        flex-direction: column;
        gap: 10px;
        padding: 10px;
        align-items: center;
    }

    .listContainer .listItem:nth-child(odd) {
        background-color: #ffffff; 
    }

    .listContainer .listItem:nth-child(even) {
        background-color: #F3F3F3;
    }

    .listContainer{
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
        outline: #000000;
        border-radius: 12px;
    }
</style>