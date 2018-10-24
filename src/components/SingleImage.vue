<template>

    <img class="imgs" :src=imagePath :alt=imageName>
</template>

<script>
    export default {
        name: "SingleImage",
        props: {
            imagePath: String,
            imageName: String,
            altName: String,

        }
    }
</script>

<style scoped>

    figure.gallery {
        border: 1px solid #ccc;
        margin: 3px;
    }

    figure.gallery img {
        width: 100%;
        height: auto;
    }

    figcaption.desc {
        padding: 15px;
        text-align: center;
    }

</style>