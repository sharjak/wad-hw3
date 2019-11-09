<template>
    <div>
        <button id="add-course-button" class="blue-button" @click="toggleForm()">+</button>
        <span v-if="showAddCourseForm" id="add-course">
            <input class="input" type="text" placeholder="Course title" id="title"/>
            <input class="input" type="number" min="1" max="8" placeholder="Semester" id="semester"/>
            <input class="input" type="number" min="0" max="100" placeholder="Grade" id="grade"/>
            <button class="green-button" id="save-course">Save</button>
            <button class="grey-button" id="cancel-course">Cancel</button>
        </span>
    </div>
</template>

<script>
    export default {
        name: "CoursesContainer",
        data: () => {
            return {
                showAddCourseForm: false
            }
        },
        methods: {
          toggleForm: function() {
              this.showAddCourseForm = !this.showAddCourseForm;
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