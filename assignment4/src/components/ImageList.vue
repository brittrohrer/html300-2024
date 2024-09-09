<script setup>

import {defineProps, ref} from "vue";
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

let isActive = ref(false);
function useBorderFunc(e, index) {
    this.isActive = !this.isActive;
    if (this.isActive === true) {
        console.log (index + ' is active');
        e.target.style.border = "solid black";
    }
    else {
        console.log (index + ' is not active');
        e.target.style.border = "none";
    }
}

</script>

<!-- 
    How we want our component structured
-->
<template>
    <div>
        <img :key="index"
            :src="prop.src"
            :alt="prop.alt"
            :class="prop.class"
            :title="prop.title"
            @click = "useBorderFunc($event, index)"
        >
    </div>
</template>

<style>

p {
    color: green;
}

</style>