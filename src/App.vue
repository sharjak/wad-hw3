<template>
    <main id="app">
        <PageHeader :title="title"/>
        <section id="container">
            <section id="main">
                <div class="content">
                    <div id="profile-container" class="tab active">
                        <ProfileContainer :user="user"/>
                    </div>
                    <div id="courses-container" class="tab">
                        <CoursesContainer />
                    </div>
                </div>

                <div class="controls">
                    <button id="profile-button" class="pill active">Profile</button>
                    <button id="courses-button" class="pill">Courses</button>
                </div>
            </section>
        </section>
        <PageFooter :footerLinks="footerLinks"/>
    </main>
</template>

<script>
    import PageHeader from "./components/PageHeader";
    import ProfileContainer from "./components/ProfileContainer";
    import CoursesContainer from "./components/CoursesContainer";
    import User from "./models/User";
    import PageFooter from "./components/PageFooter";
    import FooterLink from "./models/FooterLink";

    export default {
        name: 'app',
        components: {
            PageHeader,
            ProfileContainer,
            CoursesContainer,
            PageFooter
        },
        data: () => {
            return {
                title: 'Welcome to your dashboard!',
                user: new User('John', 'Doe', new Date(1990, 10, 10), 'Software Engineering', 2.75),
                footerLinks: [
                    new FooterLink('OIS', 'https://ois2.ut.ee/'),
                    new FooterLink('Courses', 'https://courses.cs.ut.ee/')
                ]
            }
        }
    }
</script>

<style>
    * {
        box-sizing: border-box;
        font-family: 'Livvic', sans-serif;
    }

    html, body {
        padding: 0;
        margin: 0;
        width: 100%;
        height: 100%;
        background-color: #eaeaea;
    }

    main {
        position: relative;
        min-height: 100%;
        padding-bottom: 110px;
    }

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

    table {
        width: 100%;
        border-collapse: collapse;

    }

    table th {
        padding: 8px 12px;
        text-align: left;
        border: 1px solid #cbcbcb;
        background-color: #03A9F4;
        color: #ffffff;
    }

    table td {
        padding: 8px 12px;
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

    .blue-button {
        background-color: #2196F3;
        color: #ffffff;
        border: none;
        padding: 10px 20px;
    }

    .green-button {
        background-color: #69f378;
        color: #ffffff;
        border: none;
        padding: 10px 10px;
    }

    .grey-button {
        background-color: #e1e8e6;
        color: #ffffff;
        border: none;
        padding: 10px 20px;
    }

    .input {
        border: 1px solid #cccccc;
        padding: 10px 20px;
        min-width: 135px;
    }

    #add-course {
        display: none;
    }
</style>
