<template>
    <div id="slideshow">
        <div class="carouselPics" id="cP">

            <!-- Next/previous controls -->
            <figure class="mySlides" style="display: block;"><img class="imgFixedHeigth" src="/images/butterfly.jpg"
                                                                  alt="butterfly">
                <div class="picNumber">1/4</div>
            </figure>
            <a class="prev" id="pr"><span class="prevSpan">←</span></a>
            <a class="next"><span class="nextSpan">→</span></a>


            <!-- Caption text -->
            <div class="caption-container">
                <p id="caption"></p>
            </div>
        </div>
    </div>

</template>

<script>
    export default {
        name: "Slideshow"
    }
</script>

<style scoped>

    #slideshow {
        background-color: black;
    }

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