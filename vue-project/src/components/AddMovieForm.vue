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

                <input type="submit" class="btn btn-success mt-3" value="Save movie">

            </fieldset>
        </form>
</template>
