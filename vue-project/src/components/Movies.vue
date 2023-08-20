<script setup>
    import { ref } from 'vue'
    import Movie from './Movie.vue' 
    import AddMovieForm from './AddMovieForm.vue'

    const movies = ref([]);

    let latestID = 0;

    function addMovie(movie) {
        movie.id = latestID++;
        movie.rating = parseInt(movie.rating);
        movies.value.push(movie);
    }

    function deleteMovie(e) {
        movies.value = movies.value.filter(f => {
            return f.id != e.target.attributes[1].value;
        })};

</script>
<template>
    <div class="container">
        <AddMovieForm @add-movie="addMovie"/>
        <h2>My movies</h2>
        <ul id="movies">
            <Movie v-for="movie in movies" :title="movie.title" :rating="movie.rating" :id="movie.id" @click="deleteMovie"></Movie>
        </ul>
    </div>
</template>

<style scoped>


#movies {
    padding: 1px;
    margin: 0px;
}

#movies > li {
    list-style: none;
    background-color: #eee;
    margin: 5px;
    padding: 20px;
    box-shadow: 0 0 5px #999;
    overflow:auto;
}
#movies > li > img {
    float: right;
    height: 5px;
    margin-left: 5px;
}
</style>
