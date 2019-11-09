<template>
    <section id="container">
        <section id="main">
            <div class="content">
                <div id="profile-container" class="tab" v-bind:class="{ active: isActive('profile') }">
                    <ProfileContainer :user="user"/>
                </div>
                <div id="courses-container" class="tab" v-bind:class="{ active: isActive('courses') }">
                    <CoursesContainer :courses="courses"/>
                </div>
            </div>

            <div class="controls">
                <button id="profile-button" class="pill" @click.prevent="setActive('profile')" v-bind:class="{ active: isActive('profile') }">Profile</button>
                <button id="courses-button" class="pill" @click.prevent="setActive('courses')" v-bind:class="{ active: isActive('courses') }">Courses</button>
            </div>
        </section>
    </section>
</template>

<script>
    import ProfileContainer from "./ProfileContainer";
    import CoursesContainer from "./CoursesContainer";

    export default {
        name: "SectionContainer",
        data: () => {
            return {
                activeContainer: 'profile'
            }
        },
        components: {
            ProfileContainer,
            CoursesContainer
        },
        props: {
            user: Object,
            courses: Array
        },
        methods: {
            isActive: function(container) {
                return this.activeContainer === container
            },
            setActive: function(container) {
                this.activeContainer = container
            }
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