<script setup>
    defineProps({
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
        <label>{{ title }}, {{ rating }}/5</label>
        <button class="btn btn-sm btn-danger" :data-id="id">X</button>
    </li>
</template>
