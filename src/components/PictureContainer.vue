<template>
    <div class="image">
        <img v-for="image in images" :src="picBasePath + image.name " :alt="image.name">
    </div>
</template>

<script>
    let picBasePathVar = "src/assets/images/";
    let imageList = [{'name': 'butterfly.jpg'},
        {'name': 'ducks.jpg'},
        {'name': 'fire.jpg'},
        {'name': 'kings_canyon.jpg'},
        {'name': 'koalas.jpg'},
        {'name': 'pink_flower.jpg'},
        {'name': 'stairs.jpg'},
        {'name': 'uluru.jpg'},
        {'name': 'yellow_flower.jpg'},
    ];
    export default {
        name: "PictureContainer",
        components: {},
        props: {
            picBasePath: picBasePathVar,
            images: imageList,
        }
    }


</script>

<style scoped>

</style>