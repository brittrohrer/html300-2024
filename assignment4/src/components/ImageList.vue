<script setup>

import {defineProps} from "vue";
/* 
    Create Prop with simple type validator
    Declare what type of variables and what type of data we are recieving from the parent
*/
const prop = defineProps({
        src: String,
        alt: String,
        title: String,
        class: String,
        index: Number,
});
    

</script>

<!-- 
    How we want our component structured
-->
<template>
    <div>
        <img :key="prop.src"
            :src="prop.src"
            :alt="prop.alt"
            :class="prop.class"
            :title="prop.title"
            
        >
        <p>Caption: {{prop.title}}</p>
        <p>Index: {{index}}</p>
    </div>
</template>

<style>
p {
    color: green;
}

</style>