<script>
    import CourseCard from "$lib/CourseCard.svelte";
</script>

<div id="background">
    <h1 id="h1Header">Future Cources</h1>
    <h2 id="h2Header">Semester 4</h2>
    <CourseCard courseName="COOP 4001"
        courseDescription="Student will need to do their 4th Co-op in this semester."/>
    <h2 id="h2Header">Semester 5</h2>
    <CourseCard courseName="ENGL 2001"
        courseDescription="This course is English Composition where students will learn how to write a narrative essay, and a research study in the professional world. "/>
    <CourseCard courseName="CS 4156"
        courseDescription="This course covers over operating systems using Ubuntu VM."/>
    <CourseCard courseName="3rd BOK"
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