<script>
    import DetailedCourseCard from "$lib/DetailedCourseCard.svelte";
</script>

<div id="background">
    <h1 id="h1Header">Completed Cources</h1>
    <h2 id="h2Header">Semester 2</h2>
    <DetailedCourseCard courseName="COOP 2011"
        grades="P"
        creditHours="3.00"
        professor="Mahogany Plywood"
        when="Spring Semester 2023"
        redirectURL="https://www.catalyst.uc.edu/psp/ps/EMPLOYEE/SA/c/SA_LEARNER_SERVICES.CLASS_SEARCH.GBL?a=92"
        courseDescription="Student will need to do their 1st Co-op in this semester."/>
    <h2 id="h2Header">Semester 1</h2>
    <DetailedCourseCard courseName="ENGL 2001"
        grades="C"
        creditHours="3.00"
        professor="Nomor Esays"
        when="Fall Semester 2022"
        redirectURL="https://www.catalyst.uc.edu/psp/ps/EMPLOYEE/SA/c/SA_LEARNER_SERVICES.CLASS_SEARCH.GBL?a=92"
        courseDescription="This course is English Composition where students will learn how to write a narrative essay, and a research study in the professional world. "/>
    <DetailedCourseCard courseName="CS 4156"
        grades="B"
        creditHours="3.00"
        professor="Ined Ajob"
        when="Fall Semester 2022"
        redirectURL="https://www.catalyst.uc.edu/psp/ps/EMPLOYEE/SA/c/SA_LEARNER_SERVICES.CLASS_SEARCH.GBL?a=92"
        courseDescription="This course covers over operating systems using Ubuntu VM."/>
    <DetailedCourseCard courseName="FIN 4021"
        grades="A"
        creditHours="5.00"
        professor="Howget Cash"
        when="Fall Semester 2022"
        redirectURL="https://www.catalyst.uc.edu/psp/ps/EMPLOYEE/SA/c/SA_LEARNER_SERVICES.CLASS_SEARCH.GBL?a=92"
        courseDescription="Students will learn about options, futures, forwards, and swaps."/>
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