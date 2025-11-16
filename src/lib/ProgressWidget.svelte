<script>
    import Card from "./Card.svelte";
    import ClassData from "$lib/ClassData.json";
    import CoopData from "$lib/CoopData.json"
    import PieChart from "$lib/PieChart.svelte";
    import warning from "$lib/icons/Warning.svg";
    import hourglass from "$lib/icons/HourglassTop.svg"
    import openInNew from "$lib/icons/OpenInNew.svg"
    import Button from "./Button.svelte";
    
</script>
<div class = "title">
    
        <h2>Degree Audit</h2>

    
</div>
<div class = "left_right">
<div class = "left">
   
<Card>
 
 
    <h2><img class="iconImage" src={warning} alt="warning" />
        Missing Classes</h2>
<text>These are the classes required for graduation you are missing that students in you
    program have typically taken by now.
</text>
        
            <div class = "actualCourses">
            <div class = listContainer style="width:96%;">
            <div class = listItem style="width:100%">
            <text> CS 5167 </text>
            
            <Button type="link">
            See Details
            </Button>
            </div>
            
            </div>
                
            </div>

        
        <div class="leanRightButton">
            <Button>
            See Details
            </Button>
        </div>
</Card>


<Card>
 
 
    <h2><img class="iconImage" src={hourglass} alt="hourglass" />
        In Progress Classes</h2>
<text>These are the classes in which you are currently enrolled.
</text>
        <div class = "actualCourses">
        <div class = listContainer style="width:96%;">    
        <div class = listItem style="width:100%">
            <text> CS 5167 </text>
            
            <Button type="link">
            See Details
            </Button>
        </div>
       
           
        <div class = listItem style="width:100%">
            <text> CS 5167 </text>
            
            <Button type="link">
            See Details
            </Button>
        </div>
        <div class = listItem style="width:100%">
            <text> CS 5167 </text>
            
            <Button type="link">
            See Details
            </Button><img class="iconImage" src={openInNew} alt="Open In New Tab" />
            
        </div>
        </div> 
        </div>
        <div class="leanRightButton">
            <Button>
            See Details
            </Button>
        </div>

        
</Card>
</div>
<div class = "right">
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
            <div class = "keyElipse" style="background-color:#6CC6EA"></div>
            <text> in progress </text>
            <button> Details Placeholder </button>
        </div>
        <div class = listItem>
            <div class = "keyElipse" style="background-color:#EC2542"></div> 
            <text> missing </text>
            <button> Details Placeholder </button>
        </div>
        <div class = listItem>
            <div class = "keyElipse" style="background-color:#F3F3F3"></div>
            <text> future </text>
            <button> Details Placeholder </button>
        </div>
    </div>
</Card>
</div>
</div>

<style>

    .leanRightButton {
    display: flex;
    width: 100%;
    justify-content: flex-end; /* pushes content to the right */
    align-items: flex-start;
    }
    .iconImage{
        width: 22px;
        height: 19px;
        flex-shrink: 0;
    }
    .actualCourses{
        width:100%;
        display: flex;
    padding: 5px 10px;
    align-items: center;
    gap: 10px;
    align-self: stretch;
    }
    
    .left_right{
        display:flex;
        
    }
    .left{
        display: flex;
width: 600px;
flex-direction: column;
align-items: flex-start;
gap: 10px;
margin: 10px;
align-self: stretch;
        
    }
    .right{
        display: flex;
        margin: 10px;
        
    }

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
        border: solid 1px black;
        border-radius: 12px;
    }

    .title{
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        gap: 10px;
        margin: 10px;
        align-self: stretch;
    }
</style>