<script setup>
    let props = defineProps({
        title: {
            type: String,
            required: true
        },
        rating: {
            type: String,
            required: true
        },
        id : {
            type: String,
            required: true
        }
    })
</script>
<template>
    <li class="list-group-item">
        <span>{{title}}</span>
        <span>
            <img v-for="rating of props.rating" src="./images/star.png" alt="">
        </span>
        <button class="btn btn-lg btn-danger" :data-id="id">X</button>
    </li>
</template>
