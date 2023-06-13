<script setup>
    import { ref } from 'vue'
    import Movie from './Movie.vue' 

    const films = localStorage.films;

    let latestID = 0;

    function addMovie(film) {
        film.rating = parseInt(film.rating);
        film.id = id++;
        films.value.push(film);
        console.log(films.value);
    }

</script>
<template>
    <h2>My movies</h2>
    <ul>
        <Movie v-for="film in films" :title="film.title" :rating="film.rating" :id="film.id" :key="`item-${film.id}`"></Movie>
    </ul>
</template>
