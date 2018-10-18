<template>
    <ul class="social-icon-list">
        <a href="http://facebook.com">
            <img src="../assets/icons/facebook.png">
        </a>

        <a href="http://facebook.com">
            <img src="../assets/icons/instagram.png"/>
        </a>

        <a href="http://facebook.com">
            <img src="../assets/icons/twitter.png"/>
        </a>

    </ul>
</template>

<script>
    export default {
        name: "SocialNetworksIcons"
    }
</script>

<style scoped>

    ul.social-icon-list {
        /*position: fixed;*/
        /*left: 0;*/
        /*top: 0;*/
        width: 100%;
        /*list-style-type: none;*/
        /*margin: 0;*/
        /*padding: 0;*/
        /*overflow: hidden;*/
        /*background-color: wheat;*/
        display: flex;
        flex-direction: row; /* keep the contents in a row */
        flex-wrap: wrap; /* bring contents to the next line if necessary */
        justify-content: center; /* keep the contents in the middle */
    }

</style>