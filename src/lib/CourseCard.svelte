<script>
    import Card from "./Card.svelte";
    import Button from "./Button.svelte";
    
    export let courseName = "Course Name";
    export let courseDescription = "This is a description of the course.";
    export let redirectURL = "#";
</script>

<Card>
    <p id="courseName">{courseName}</p>
    <Button id="redirectURL" on:click={() => window.location.href = redirectURL}>
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none">
            <path d="M5 21C4.45 21 3.97933 20.8043 3.588 20.413C3.19667 20.0217 3.00067 19.5507 3 19V5C3 4.45 3.196 3.97933 3.588 3.588C3.98 3.19667 4.45067 3.00067 5 3H12V5H5V19H19V12H21V19C21 19.55 20.8043 20.021 20.413 20.413C20.0217 20.805 19.5507 21.0007 19 21H5ZM9.7 15.7L8.3 14.3L17.6 5H14V3H21V10H19V6.4L9.7 15.7Z" fill="black"/>
        </svg>
    </Button>
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

#redirectURL {
    width: 30px;
    height: 30px;
    flex-shrink: 0;
    margin: 0;
    padding: 0;
    color: white;
    position: absolute;
    right: 25px;
    top: 15px;
    fill: var(--Primary-UC-Black, #000);
    aspect-ratio: 1/1;
}

</style>