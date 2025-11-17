<script>
    import Card from "./Card.svelte";
    import Button from "./Button.svelte";

    export let courseName = "Course Name";
    export let courseDescription = "This is a description of the course.";
    export let redirectURL = "#";
    
    export let grades = "Grade: F";
    export let creditHours = "Units: 0.0";
    export let professor = "Professor: Firstname Lastname";
    export let when = "When: N/A";
</script>

<Card>
    <Button id="redirectURL" on:click={() => window.location.href = redirectURL}>
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none">
            <path d="M5 21C4.45 21 3.97933 20.8043 3.588 20.413C3.19667 20.0217 3.00067 19.5507 3 19V5C3 4.45 3.196 3.97933 3.588 3.588C3.98 3.19667 4.45067 3.00067 5 3H12V5H5V19H19V12H21V19C21 19.55 20.8043 20.021 20.413 20.413C20.0217 20.805 19.5507 21.0007 19 21H5ZM9.7 15.7L8.3 14.3L17.6 5H14V3H21V10H19V6.4L9.7 15.7Z" fill="black"/>
        </svg>
    </Button>

    <div id="infoholder">
        <p id="courseName">{courseName}</p>
        <div id="divider"></div>

        <div id="info1">
            <p class="detailtext">{grades}</p>
            <p class="detailtext">{creditHours}</p>
        </div>

        <div id="info2">
            <p class="detailtext">{professor}</p>
            <p class="detailtext">{when}</p>
        </div>
    </div>
    
    <p id="courseDescription">{courseDescription}</p>
</Card>

<style>

.detailtext {
    display: flex;
    height: 25px;
    flex-direction: column;
    justify-content: center;
    align-self: stretch;
    color: #000;
    font-family: "Noto Sans";
    font-size: 12px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
}

#courseName {
    display: flex;
    width: 150px;
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

#infoholder {
    display: flex;
    width: 760px;
    height: 54px;
    padding: 0 10px;
    align-items: center;
    gap: 9px;
    flex-shrink: 0;
    }

#divider {
    width: 260px;
    height: 54px;
    flex-shrink: 0;
}

#info1 {
    display: flex;
    width: 95px;
    flex-direction: column;
    align-items: flex-start;
    flex-shrink: 0;
}

#info2 {
    display: flex;
    width: 215px;
    flex-direction: column;
    align-items: flex-start;
    flex-shrink: 0;
}

</style>