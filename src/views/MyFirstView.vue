<template>
    <p class="green-background"> {{welcomeMsg}}</p>
</template>

<script>
    export default {
        name: "MyFirstView",
        props:{
            welcomeMsg : String
        }
    }
</script>

<style scoped>

    .green-background{
        background: #4fc08d;
    }

</style>