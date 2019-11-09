<template>
    <main id="app">
        <PageHeader :title="title"/>
        <SectionContainer :user="user"/>
        <PageFooter :footerLinks="footerLinks"/>
    </main>
</template>

<script>
    import PageHeader from "./components/PageHeader";
    import User from "./models/User";
    import PageFooter from "./components/PageFooter";
    import FooterLink from "./models/FooterLink";
    import SectionContainer from "./components/SectionContainer";

    export default {
        name: 'app',
        components: {
            PageHeader,
            SectionContainer,
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
