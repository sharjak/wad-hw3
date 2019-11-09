<template>
    <section id="container">
        <section id="main">
            <div class="content">
                <div id="profile-container" class="tab">
                    <ProfileContainer :user="user"/>
                </div>
                <div id="courses-container" class="tab active">
                    <CoursesContainer :courses="courses"/>
                </div>
            </div>

            <div class="controls">
                <button id="profile-button" class="pill">Profile</button>
                <button id="courses-button" class="pill active">Courses</button>
            </div>
        </section>
    </section>
</template>

<script>
    import ProfileContainer from "./ProfileContainer";
    import CoursesContainer from "./CoursesContainer";

    export default {
        name: "SectionContainer",
        components : {
            ProfileContainer,
            CoursesContainer
        },
        props: {
            user: Object,
            courses: Array
        }
    }
</script>

<style>
    #container {
        width: 80%;
        max-width: 900px;
        min-width: 320px;
        padding: 15px;
        background-color: #ffffff;
        margin: 0 auto;
    }

    .content {
        padding: 10px;
        border: 1px solid #cbcbcb;
    }

    .content .tab {
        display: none;
    }

    .content .tab.active {
        display: block;
    }

    .controls .pill {
        border: 1px solid #cbcbcb;
        background-color: #eaeaea;
        padding: 10px;
        border-bottom-left-radius: 4px;
        border-bottom-right-radius: 4px;
        border-top: none;
        margin-top: -1px;
        outline: none !important;
    }

    .controls .pill.active {
        background-color: #ffffff;
        border-top: 1px solid #ffffff;
    }

    .controls .pill:hover {
        cursor: pointer;
    }
</style>