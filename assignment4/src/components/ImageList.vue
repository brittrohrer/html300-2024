<script setup>
    import {defineProps, ref } from "vue";
    // Create Prop with simple type validator
    const prop = defineProps({
        link: String,
        text: Number,
        title: String,
        class: String,
    });
</script>

<template>

    <img 
    :src='prop.link' 
    :alt='prop.text' 
    :title='prop.title'
    :class='prop.class'
    >

</template>

<style>

</style>