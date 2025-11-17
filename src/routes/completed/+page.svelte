<script>
    import DetailedCourseCard from "$lib/DetailedCourseCard.svelte";
</script>

<div id="background">
    <h1 id="h1Header">Completed Cources</h1>
    <h2 id="h2Header">Semester 2</h2>
    <DetailedCourseCard courseName="COOP 4001"
        courseDescription="Student will need to do their 4th Co-op in this semester."/>
    <h2 id="h2Header">Semester 1</h2>
    <DetailedCourseCard courseName="ENGL 2001"
        courseDescription="This course is English Composition where students will learn how to write a narrative essay, and a research study in the professional world. "/>
    <DetailedCourseCard courseName="CS 4156"
        courseDescription="This course covers over operating systems using Ubuntu VM."/>
    <DetailedCourseCard courseName="3rd BOK"
        courseDescription="Students will need to take their 3rd BOK this semester. Open the popup link to see the courses available and eligible for this credit."/>
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