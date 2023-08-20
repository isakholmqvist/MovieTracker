<script setup>
    let props = defineProps({
        title: {
            type: String,
            required: true
        },
        rating: {
            type: Number,
            required: true
        },
        id : {
            type: Number,
            required: true
        }
    })
</script>
<template>
        <li class="list-group-item">
        <span>{{title}}</span>
        <div class="row">
            <span>
                <img v-for="rating of props.rating" src="./images/star.png" alt="" class="img-fluid">
            </span>
        </div>
        <button class="btn btn-lg btn-danger" :data-id="id">X</button>
        </li>
</template>

