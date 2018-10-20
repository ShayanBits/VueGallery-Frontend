<template>
    <div class="about">
        <h1>This is an about page</h1>
        <Footer/>
    </div>
</template>

<script>
    import MyFirstView from "./MyFirstView";
    import Footer from "../components/Footer";
    export default {
        components: {Footer, MyFirstView}
    }
</script>