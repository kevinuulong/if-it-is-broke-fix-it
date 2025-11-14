<script>
    import Card from "./Card.svelte"; 
    export let courseName = "Course Name";
    export let courseDescription = "This is a description of the course.";
    export let redirectURL = "#";
</script>

<Card>
    <p id="courseName">{courseName}</p>
    <p id="courseDescription">{courseDescription}</p>
</Card>

<style>
#courseName {
    display: flex;
    width: 800px;
    height: 54px;
    flex-direction: column;
    justify-content: center;
    flex-shrink: 0;
    color: #000;
    font-family: "Noto Sans";
    font-size: 24px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
}

#courseDescription {
    width: 800px;
    height: 65px;
    flex-shrink: 0;
    color: #000;
    font-family: "Noto Sans";
    font-size: 16px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
}
</style>