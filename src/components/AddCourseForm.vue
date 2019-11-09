<template>
    <div>
        <button id="add-course-button" class="blue-button" @click="toggleForm()">+</button>
        <span v-if="showAddCourseForm" id="add-course">
            <input class="input" type="text" placeholder="Course title" id="title" v-model="title"/>
            <input class="input" type="number" min="1" max="8" placeholder="Semester" id="semester" v-model="semester"/>
            <input class="input" type="number" min="0" max="100" placeholder="Grade" id="grade" v-model="grade"/>
            <button class="green-button" id="save-course" @click="addNewCourse()">Save</button>
            <button class="grey-button" id="cancel-course">Cancel</button>
        </span>
    </div>
</template>

<script>
    import Course from "../models/Course";

    export default {
        name: "AddCourseForm",
        data: () => {
            return {
                showAddCourseForm: false,
                title: "",
                semester: "",
                grade: ""   
            }
        },
        props: {
            courses: Array
        },
        methods: {
            toggleForm: function() {
                this.showAddCourseForm = !this.showAddCourseForm;
            },
            addNewCourse: function() {
                var coursetitle = this.title
                var coursesemester = this.semester
                var coursegrade = this.grade
            
                this.courses.push(new Course(coursetitle, coursesemester, coursegrade))
                this.title = ""
                this.semester = ""
                this.grade = ""
            }   
        }
    };
</script>

<style>
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

</style>