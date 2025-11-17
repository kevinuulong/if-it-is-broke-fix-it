<script>
    import Card from "./Card.svelte";
    import ClassData from "$lib/ClassData.json";
    import CoopData from "$lib/CoopData.json";
    import PieChart from "$lib/PieChart.svelte";
    import warning from "$lib/icons/Warning.svg";
    import hourglass from "$lib/icons/HourglassTop.svg";
    import openInNew from "$lib/icons/OpenInNew.svg?raw";
    import Button from "./Button.svelte";
</script>

<div class="title">
    <h2>Degree Audit</h2>
</div>
<div class="left_right">
    <div class="left">
        <Card>
            <div class="gap">
                <img class="iconImage" src={warning} alt="Warning" />
                <h2>Missing Classes</h2>
            </div>
            <div class="actualCourses">
                <p style="width:100%">
                    These are the classes required for graduation you are
                    missing that students in you program have typically taken by
                    now.
                </p>

                <div class="listContainer" style="width:100%;">
                    <div class="listItem">
                        <p>CS 5167</p>
                        <div>
                            <Button
                                type="link"
                                icon={openInNew}
                                href="https://uc.collegescheduler.com/"
                                target="_blank"
                            >
                                Plan Course
                            </Button>
                        </div>
                    </div>
                    <div class="listItem">
                        <p>CS 5124</p>
                        <div>
                            <Button
                                type="link"
                                icon={openInNew}
                                href="https://uc.collegescheduler.com/"
                                target="_blank"
                            >
                                Plan Course
                            </Button>
                        </div>
                    </div>
                </div>
                <div>
                    <Button
                    type="primary"
                    href="https://www.catalyst.uc.edu/psp/ps/EMPLOYEE/SA/c/SA_LEARNER_SERVICES.CLASS_SEARCH.GBL?a=92"
                    >See Details</Button>
                </div>
            </div>
        </Card>

        <Card>
            <div class="gap">
                <img class="iconImage" src={hourglass} alt="In Progress" />

                <h2>In Progress</h2>
            </div>
            <div class="actualCourses">
                <p style="width:100%">
                    These are the classes in which you are currently enrolled.
                </p>

                <div class="listContainer" style="width:100%;">
                    <div class="listItem">
                        <p>CS 5170</p>
                        <Button
                    type="link"
                    href="https://www.catalyst.uc.edu/psp/ps/EMPLOYEE/SA/c/SA_LEARNER_SERVICES.CLASS_SEARCH.GBL?a=92"
                >
                    See Details
                </Button>
                    </div>
                    <div class="listItem">
                        <p>EECE 5136</p>
                        <Button
                    type="link"
                    href="https://www.catalyst.uc.edu/psp/ps/EMPLOYEE/SA/c/SA_LEARNER_SERVICES.CLASS_SEARCH.GBL?a=92"
                >
                    See Details
                </Button>
                    </div>
                    <div class="listItem">
                        <p>FAA 1062</p>
                        <Button
                    type="link"
                    href="https://www.catalyst.uc.edu/psp/ps/EMPLOYEE/SA/c/SA_LEARNER_SERVICES.CLASS_SEARCH.GBL?a=92"
                >
                    See Details
                </Button>
                    </div>
                </div>

                <Button
                    
                    type="primary"
                    href="https://www.catalyst.uc.edu/psp/ps/EMPLOYEE/SA/c/SA_LEARNER_SERVICES.SSR_SSENRL_LIST.GBL?a=92"
                >
                    See Details
                </Button>
            </div>
        </Card>
    </div>
    <div class="right">
        <Card>
            <h2>Degree Progress</h2>

            <div class="charts">
                <div class="pieChart">
                    <PieChart data={ClassData} />
                    <text>Classes</text>
                </div>
                <div class="pieChart">
                    <PieChart data={CoopData} />
                    <text>Co-op</text>
                </div>
            </div>

            <div class="listContainer">
                <div class="listItem">
                    <div
                        class="keyElipse"
                        style="background-color:#25EC93"
                    ></div>
                    <text> complete </text>
                    <Button type="tertiary" href="./complete">See details</Button>
                </div>
                <div class="listItem">
                    <div
                        class="keyElipse"
                        style="background-color:#6CC6EA"
                    ></div>
                    <text> in progress </text>
                    <Button type="tertiary">See details</Button>
                </div>
                <div class="listItem">
                    <div
                        class="keyElipse"
                        style="background-color:#EC2542"
                    ></div>
                    <text> missing </text>
                    <Button type="tertiary" href="./missing">See details</Button>
                </div>
                <div class="listItem">
                    <div
                        class="keyElipse"
                        style="background-color:#F3F3F3"
                    ></div>
                    <text> future </text>
                    <Button type="tertiary" href="./future">See details</Button>
                </div>
            </div>
        </Card>
    </div>
</div>

<style>
    
    .gap {
        display: flex;

        align-items: center;
        justify-content: left;
        gap: 20px;
    }

    .iconImage {
        width: 22px;
        height: 19px;
        flex-shrink: 0;
    }
    .actualCourses {
        display: flex;
        padding-left: 48px;
        flex-direction: column;
        align-items: flex-end;
        gap: 20px;
        align-self: stretch;
    }

    .left_right {
        display: flex;
    }
    .left_right {
        display: flex;
    }
    .left {
        display: flex;
        width: 600px;
        flex-direction: column;
        align-items: flex-start;
        gap: 10px;
        margin: 10px;
        align-self: stretch;
    }
    .right {
        display: flex;
        margin: 10px;
    }

    .charts {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 20px;
        align-self: stretch;
    }

    .pieChart {
        display: flex;
        flex-direction: column;
        gap: 10px;
        padding: 10px;
        align-items: center;
    }

    .listContainer .listItem:nth-child(odd) {
        background-color: #ffffff;
    }

    .listContainer .listItem:nth-child(even) {
        background-color: #f3f3f3;
    }

    .listContainer {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        align-self: stretch;
    }

    .listItem {
        display: flex;
        padding: 5px 10px;
        align-items: center;
        gap: 10px;
        align-self: stretch;
        justify-content: space-between;
    }

    .keyElipse {
        width: 24px;
        height: 24px;
        aspect-ratio: 1/1;
        border: solid 1px black;
        border-radius: 12px;
    }

    .title {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        gap: 10px;
        margin: 10px;
        align-self: stretch;
    }
</style>
