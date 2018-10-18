<template>
    <div class="about">
        <h1>This is an about page</h1>
        <MyFirstView welcome-msg="Your welcome message!"/>
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