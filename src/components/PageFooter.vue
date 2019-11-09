<template>
    <footer>
        <ul class="links">
            <li v-for="footerLink in footerLinks" v-bind:key="footerLink.name">
                <a :href="footerLink.url" target="_blank">{{footerLink.name}}</a>
            </li>
        </ul>
    </footer>
</template>

<script>
    export default {
        name: "PageFooter",
        props: {
            footerLinks: Array
        }
    }
</script>

<style>
    footer {
        padding: 30px 0;
        background-color: #607D8B;
        margin-top: 10px;
        height: 100px;
        position: absolute;
        bottom: 0;
        width: 100%;
    }

    footer .links {
        display: block;
        width: 100%;
        max-width: 200px;
        margin: 0 auto;
        color: #acd7ff;
        font-size: 11px;
    }

    footer .links a {
        text-decoration: none;
        color: #acd7ff;
    }

    footer .links a:hover {
        text-decoration: underline;
    }
</style>
