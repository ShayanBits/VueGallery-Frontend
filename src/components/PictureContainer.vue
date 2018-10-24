<template>
    <div id="galleryPage">
        <div class="picContainer">
            <div v-for="image in images" class="responsive">
                <figure class="gallery"><img :src="picBasePath +image.name + '.jpg' " :alt="image.name">
                    <figcaption class="desc">{{image.name}}</figcaption>
                </figure>
            </div>
        </div>
    </div>
</template>

<script>
    import SingleImage from "./SingleImage";

    let picBasePathVar = "/images/";
    let imageList = [{'name': 'butterfly'},
        {'name': 'ducks'},
        {'name': 'fire'},
        {'name': 'kings_canyon'},
        {'name': 'koalas'},
        {'name': 'pink_flower'},
        {'name': 'stairs'},
        {'name': 'uluru'},
        {'name': 'yellow_flower'},
    ];
    export default {
        name: "PictureContainer",
        data() {
            return {
                picBasePath: picBasePathVar,
                images: imageList,
            }
        },
        components: {SingleImage}
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

    * {
        box-sizing: border-box;
    }

    .responsive {
        padding: 0 6px;
        width: 33.0%;
    }

    .picContainer{
        display: flex;
        flex-wrap: wrap;
    }

    @media only screen and (max-width: 700px) {
        .responsive {
            width: 49.99999%;
            margin: 6px 0;
        }
    }

    @media only screen and (max-width: 500px) {
        .responsive {
            width: 100%;
        }
    }
</style>