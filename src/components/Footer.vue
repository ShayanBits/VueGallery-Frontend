<template>
    <footer>
        <SocialNetworksIcons></SocialNetworksIcons>
        <div>© 2018 LOGO</div>
    </footer>
</template>

<script>
    import SocialNetworksIcons from "./SocialNetworksIcons";

    export default {
        name: "Footer",
        components: {SocialNetworksIcons}
    }
</script>

<style scoped>

    footer {
        position: fixed;
        background-color: #2c3e50;
        left: 0;
        bottom: 0;
        width: 100%;
        text-align: center;
        justify-content: center;
        color: #637688;
    }
</style>