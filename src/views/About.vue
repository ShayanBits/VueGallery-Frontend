<template>
  <div class="about">
    <h1>This is an about page</h1>
    <MyFirstVue welcomeMsg="this works!"/>
  </div>
</template>
<script>
    import MyFirstView from "./MyFirstView";

    export default {
        components: { MyFirstView}
    }
</script>