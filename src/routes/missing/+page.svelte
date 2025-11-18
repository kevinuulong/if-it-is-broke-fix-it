<script>
    import CourseCard from "$lib/CourseCard.svelte";
</script>

<div id="background">
    <h1 id="h1Header">Degree Audit</h1>
    <h2 id="h2Header">Missing Courses</h2>
    <CourseCard courseName="CS 5167"
        redirectURL="#"
        courseDescription="This course introduces the basic concepts of human computer interaction and the latest development of the technology for developing interactive systems."/>
    <CourseCard courseName="CS 5124"
        redirectURL="#"
        courseDescription="This course introduces students to data visualization - a computer science research area that uses methods in human-centered computing to address contemporary data science challenges."/>
</div>

<style>
#background {
    display: flex;
    padding: 20px 30px;
    flex-direction: column;
    align-items: flex-start;
    gap: 20px;
    flex: 1 0 0;
    align-self: stretch;
}

#h1Header {
    color: #000;
    font-family: "Noto Sans";
    font-size: 36px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
}

#h2Header{
    color: #000;
    font-family: "Noto Sans";
    font-size: 24px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
}

</style>