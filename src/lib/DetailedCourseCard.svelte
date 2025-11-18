<script>
    import Card from "./Card.svelte";
    import Button from "./Button.svelte";
    import openInNew from "$lib/icons/OpenInNew.svg?raw";

    export let courseName = "Course Name";
    export let courseDescription = "This is a description of the course.";
    export let redirectURL = "#";
    
    export let grades = "F";
    export let creditHours = "0.00";
    export let professor = "Firstname Lastname";
    export let when = "N/A";
</script>

<Card>
    <div id="redirectURL">
        <Button on:click={() => window.location.href = redirectURL}
        type="tertiary"
        href={redirectURL}
        icon={openInNew}
        target="_blank"/>
    </div>

    <div id="infoholder">
        <p id="courseName">{courseName}</p>
        <div id="divider"></div>

        <div id="info1">
            <p class="detailtext">Grade: {grades}</p>
            <p class="detailtext">Units: {creditHours}</p>
        </div>

        <div id="info2">
            <p class="detailtext">Professor: {professor}</p>
            <p class="detailtext">When: {when}</p>
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
    padding: 0;
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