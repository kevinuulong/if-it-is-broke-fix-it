<script>
    import CourseCard from "$lib/CourseCard.svelte";
</script>

<div id="background">
    <h1 id="h1Header">Future Cources</h1>
    <h2 id="h2Header">Semester 4</h2>
    <CourseCard courseName="COOP 4001"
        redirectURL="#"
        courseDescription="Student will need to do their 4th Co-op in this semester."/>
    <h2 id="h2Header">Semester 5</h2>
    <CourseCard courseName="CS 5002"
        redirectURL="#"
        courseDescription="Second of two semester laboratory series in which students create a significant product capitalizing on their prior four years of computer science education."/>
    <CourseCard courseName="CS 5125"
        redirectURL="#"
        courseDescription="This is an introduction course to the fields of data compression, data encryption, and error detection at the senior undergraduate and beginning graduate level."/>
    <CourseCard courseName="3rd BOK"
        redirectURL="#"
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