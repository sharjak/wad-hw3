<template>
    <div>
        <h1 class="title">Courses</h1>
        <table id="courses">
            <thead>
            <tr>
                <th>#</th>
                <th>Course Title</th>
                <th>Semester</th>
                <th>Grade</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="(course, index) in courses" v-bind:key="course.name">
                <td>{{index+1}}</td>
                <td v-for="value in Object.values(course)" v-bind:key="value">
                    {{value}}
                </td>
            </tr>
            </tbody>
        </table>
        <br/>
        <br/>
        <AddCourseForm :courses="courses"/>
    </div>
</template>

<script>
    import AddCourseForm from "./AddCourseForm";

    export default {
        name: "CoursesContainer",
        components: {
            AddCourseForm
        },
        props: {
            courses: Array
        },
    };
</script>

<style>
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
</style>