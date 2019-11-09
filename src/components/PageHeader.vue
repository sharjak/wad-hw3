<template>
    <header>
        <strong>{{title}}</strong>
    </header>
</template>

<script>
    export default {
        name: "PageHeader",
        props: {
            title: String
        }
    }
</script>

<style>
    header {
        padding: 20px;
        background-color: #2196F3;
        color: #ffffff;
        text-align: center;
        margin-bottom: 10px;
        height: 60px;
    }
</style>