<script setup>
    import { ref, onMounted } from 'vue';
    import Movies from './Movies.vue';
    
    const emit = defineEmits(['add-movie']);
    const movies = []

    function addMovie(object) {
        let title = document.querySelector("#title-field");
        let rating = document.querySelector("#rating-field");
        const movie = {
            title: title.value,
            rating: rating.value
        }
        title.value = "";
        rating.value = "";
        console.log(title, rating);

        movies.push(movie);

        localStorage.setItem('movies', JSON.stringify(movies));

        emit("add-movie", object);
        
    }
 
    let latestID = 0;

</script>
<template>
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
                    <option value="5">5</option>
                </select>

                <input type="button" class="btn btn-success mt-3" value="Save movie" @click="addMovie">

            </fieldset>
        </form>
        <Movies v-for="film in films" :title="film.title"/>
</template>
