<script setup>
    const emit = defineEmits(['add-movie']);

    function addMovie(object) {
        document.getElementById("add-movie-form").reset();
        emit("add-movie", object);
    }

    function submit(e) {
        e.preventDefault();
        const title = document.querySelector("#title-field");
        const rating = document.querySelector("#rating-field");
        if (!(title.value === "" || rating.value == 0)) {
            let object = {title: title.value, rating: rating.value};
            addMovie(object);
        } else {
            alert("Fill in the correct information");
        }
    }

</script>
<template>
    <div class="container">
        <h1>Min filmlista</h1>
        <form id="add-movie-form">
            <fieldset>
                <legend>Add a movie</legend>

                <label for="title-field">Title:</label>
                <input type="text" id="title-field" class="form-control">

                <label for="rating-field">Rating:</label>
                <select type="text" id="rating-field" class="form-control">
                    <option value="0">Choose rating...</option>
                    <option value="1">1</option>
                    <option value="2">2</option>
                    <option value="3">3</option>
                    <option value="4">4</option>
                    <option valre="5">5</option>
                </select>
                <input type="button" class="btn btn-success mt-3" value="Save movie" @click="submit">
            </fieldset>
        </form>
    </div>
</template>
