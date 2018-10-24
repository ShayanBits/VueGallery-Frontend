<template>
    <div id="galleryPage">
        <div class="picContainer">
            <div v-for="image in images" class="responsive">
                <figure v-on:click="showImage(image.index)" class="gallery"><img :id="image.name"
                                                                                                :src="picBasePath +image.name + '.jpg' "
                                                                                                :alt="image.name">
                    <figcaption class="desc">{{image.name}}</figcaption>
                </figure>
            </div>
        </div>

        <div id="overlayCarousel" class="carousel"></div>

        <div class="carouselPics" id="cP">

            <figure v-for="image in images" class="mySlides" style="display: none;">
                <img class="imgFixedHeigth" :id="image.name"
                     :src="picBasePath +image.name + '.jpg' "
                     :alt="image.name">
                <div class="picNumber">{{image.index}}</div>
            </figure>

            <!-- Next/previous controls -->
            <a class="prev" id="pr"><span class="prevSpan">&larr;</span></a>
            <a class="next"><span class="nextSpan">&rarr;</span></a>


            <!-- Caption text -->
            <div class="caption-container">
                <p id="caption"></p>
            </div>
        </div>
    </div>
</template>

<script>
    import SingleImage from "./SingleImage";

    let picBasePathVar = "/images/";
    let imageList = [{'name': 'butterfly', 'index': 0},
        {'name': 'ducks', 'index': 1},
        {'name': 'fire', 'index': 2},
        {'name': 'kings_canyon', 'index': 3},
        {'name': 'koalas', 'index': 4},
        {'name': 'pink_flower', 'index': 5},
        {'name': 'stairs', 'index': 6},
        {'name': 'uluru', 'index': 7},
        {'name': 'yellow_flower', 'index': 8},
    ];
    export default {
        name: "PictureContainer",
        data() {
            return {
                picBasePath: picBasePathVar,
                images: imageList,
                currentSlide : 0,
                imgs : document.getElementsByClassName("imgs"),
                imgFixedHeigth : document.getElementsByClassName("imgFixedHeigth")

            }
        },
        components: {SingleImage},
        props: {
            imageList: imageList,
            basePath: picBasePathVar
        },
        methods: {
            openCarousel: function () {
                document.getElementById('overlayCarousel').style.display = "block";
                document.getElementsByClassName('carouselPics').style.display = "block";
            },
            closeCarousel: function () {
                document.getElementById('overlayCarousel').style.display = "none";
                document.getElementsByClassName('carouselPics')[0].style.display = "none";
            },
            showImage: function showImage(n) {
                this.openCarousel();
                let i;
                let number = document.getElementsByClassName("picNumber");
                let slides = document.getElementsByClassName("mySlides");
                if (n >= slides.length) {
                    n = 0;
                }
                if (n < 0) {
                    n = slides.length - 1;
                }
                for (i = 0; i < this.imageList.length; i++) {
                    this.imageList[i].style.display = "none";
                }
                slides[n].style.display = "block";
                number[n].innerHTML = n + 1 + '/' + slides.length;
                //currentSlide = n;
            },
            nextSlide: function nextSlide() {
                showImage(currentSlide + 1);
            },
            prevSlide: function prevSlide() {
                showImage(currentSlide - 1);
            }


        }
    }


</script>

<style>

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

    .picContainer {
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

    /*Carousel Overlay*/

    .carousel {
        display: none;
        position: fixed;
        z-index: 1;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        overflow: auto;
        background-color: black;
    }

    .imgFixedHeigth {
        height: auto;
        width: 100%;
    }

    .carouselPics {
        position: absolute;
        margin: auto;
        padding: 0;
        width: 100%;
        max-width: 1200px;
        top: 16%;
        z-index: 2;
    }

    .close {
        color: white;
        position: absolute;
        top: 10px;
        right: 25px;
        font-size: 35px;
        font-weight: bold;
    }

    .close:hover,
    .close:focus {
        color: #999;
        text-decoration: none;
        cursor: pointer;
    }

    .mySlides {
        display: none;
        width: 70%;
        margin: auto;
    }

    .prev,
    .next {
        cursor: pointer;
        position: absolute;
        top: 0;
        width: 20%;
        color: white;
        font-size: 20px;
        transition: 0.6s ease;
        border-radius: 0 3px 3px 0;
        height: 100%;
        text-align: center;
    }

    .picNumber {
        color: #f2f2f2;
        text-align: center;
        top: 100%;
    }

    .next {
        right: 15%;
    }

    .prev {
        left: 15%;
    }

    .prev:hover,
    .next:hover {
        background-color: rgba(0, 0, 0, 0.8);
    }

    .prev:hover .prevSpan,
    .next:hover .nextSpan {
        display: block;
    }

    .prevSpan,
    .nextSpan {
        position: relative;
        top: 50%;
        display: none;
    }
</style>