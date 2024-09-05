<script setup>
    import {defineProps, ref } from "vue";
    const props = defineProps ({
        link: String,
        text: String,
        title: String,
    })
</script>

<template>

    <img :src='props.link' :alt='props.text' :title='props.title'>

</template>

<style>

</style>