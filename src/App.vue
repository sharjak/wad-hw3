<template>
    <main id="app">
        <PageHeader :title="title"/>
        <SectionContainer :user="user" :courses="courses" :calculateGPA="calculateGPA"/>
        <PageFooter :footerLinks="footerLinks"/>
    </main>
</template>

<script>
    import PageHeader from "./components/PageHeader";
    import User from "./models/User";
    import PageFooter from "./components/PageFooter";
    import FooterLink from "./models/FooterLink";
    import SectionContainer from "./components/SectionContainer";
    import Course from "./models/Course";

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
                user: new User('John', 'Doe', new Date(1990, 10, 10), 'Software Engineering'),
                courses: [
                    new Course('Agile software development', 1, 82),
                    new Course('System modeling', 1, 85),
                    new Course('Object-oriented programming', 2, 99),
                    new Course('Estonian language Level A2', 2, 65)
                ],
                footerLinks: [
                    new FooterLink('OIS', 'https://ois2.ut.ee/'),
                    new FooterLink('Courses', 'https://courses.cs.ut.ee/')
                ]
            }
        },
        methods: {
            calculateGPA: function() {
                var sum = 0

                for (let i = 0; i < this.courses.length; i++) {
                    var grade = this.courses[i].grade
                    //console.log(grade)
                    if (grade > 90) sum += 4;
                    else if (grade > 80) sum += 3;
                    else if (grade > 70) sum += 2;
                    else if (grade > 60) sum += 1;
                    else if (grade > 50) sum += 0.5;
                }

                var GPA = Math.round((sum / this.courses.length) * 100) / 100
                this.user.gpa = GPA
                return GPA
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
</style>
