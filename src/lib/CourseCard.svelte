<script>
    import Card from "./Card.svelte";
    import Button from "./Button.svelte";
    import openInNew from "$lib/icons/OpenInNew.svg?raw";

    export let courseName = "Course Name";
    export let courseDescription = "This is a description of the course.";
    export let redirectURL = "#";
</script>

<Card>
    <p id="courseName">{courseName}</p>

    <div id="redirectURL">
        <Button on:click={() => window.location.href = redirectURL}
        type="link"
        href={redirectURL}
        icon={openInNew}
        target="_blank"/>
    </div>

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