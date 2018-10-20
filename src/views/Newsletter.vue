<template>
    <div>
        <h1>Newsletter</h1>
        <div class="newsletter">
            <label for="firstname"> First name </label>
            <input type="text" id="firstname" name="firstname" placeholder="Max"/><br/>

            <label for="lastname"> Last name </label>
            <input type="text" id="lastname" name="lastname" placeholder="Amini"/><br/>

            <label for="birthdate"> Birth date </label>
            <input type="date" id="birthdate"/><br/>

            <label for="email"> Email </label>
            <input type="email" id="email" name="email" placeholder="max.amini@example.com"/><br/>

            <label for="address"> Address </label>
            <input type="text" id="address" name="address" placeholder="Koenigsalee 1"/><br/>

            <label for="country"> country </label>
            <select id="country" name="country">
                <option value="USA"> USA</option>
                <option value="Iran"> Iran</option>
                <option value="France"> France</option>
                <option value="Spain"> Spain</option>
            </select> <br/>

            <label for="favoriteColor">Your favorite color </label>
            <input type="color" id="favoriteColor"/><br/>

            <input type="checkbox" id="Privacy_&_Policy"/>
            <label for="Privacy_&_Policy" class="privacypolicy"> I am known of the fact that my data on this website can be used for performance and
                advertising aavtivities</label><br/>

            <label for="feedback"> Feedback</label><br/>
            <textarea id="feedback" name="feedback" placeholder="your feedback here ..."></textarea><br/>


            <button id="submit">Submit</button><br/>
        </div>
        <Footer/>
    </div>
</template>

<script>
    import Footer from "../components/Footer";
    export default {
        name: "Newsletter",
        components: {Footer}
    }
</script>

<style scoped>

    input[type=text],input[type=email], select, textarea {
        width: 25%;
    }

</style>