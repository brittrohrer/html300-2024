<script setup>
import { ref } from "vue";

const name = ref("GridPage");

const headerOne =ref("First Container Title")
const gridOne = ref([
    {
        title: `col 1`,
        body: `Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt accusamus numquam tenetur 
                        fugiat minus asperiores inventore, nulla harum odio ducimus.`
    },
    {
        title: `col 2`,
        body: `Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt accusamus numquam tenetur 
                        fugiat minus asperiores inventore, nulla harum odio ducimus.`
    },
    {
        title: `col 3`,
        body: `Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt accusamus numquam tenetur 
                        fugiat minus asperiores inventore, nulla harum odio ducimus.`               
    },
    {
        title: `col 4`,
        body: `Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt accusamus numquam tenetur 
                        fugiat minus asperiores inventore, nulla harum odio ducimus.`
    },
],);
const headerTwo = ref("Second Grid Container")
const gridTwo = ref([
    {
        class: `col-lg-6`,
        title: `col 1`,
        body: `Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt accusamus numquam tenetur 
                        fugiat minus asperiores inventore, nulla harum odio ducimus.`
    },
    {
        class: `col-lg-3 text-center`,
        title: `col 2`,
        body: `Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt accusamus numquam tenetur 
                        fugiat minus asperiores inventore, nulla harum odio ducimus.`
    },
    {
        class: `col-lg-3 text-center`,
        title: `col 3`,
        body: `Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt accusamus numquam tenetur 
                        fugiat minus asperiores inventore, nulla harum odio ducimus.`               
    },
],);
const headerThree = ref("Third Grid Container")
const gridThree = ref([
    {
        class: `col-sm-6`,
        title: `col 1`,
        body: `Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt accusamus numquam tenetur 
                        fugiat minus asperiores inventore, nulla harum odio ducimus.`
    },
    {
        class: `col-sm-6`,
        title: `col 2`,
        body: `Lorem ipsum dolor sit, amet consectetur adipisicing elit. Deserunt accusamus numquam tenetur 
                        fugiat minus asperiores inventore, nulla harum odio ducimus.`
    },
],);
</script>

<template>
    <main>
        
        <div class="row bg-primary">
            <h2>{{headerOne}}</h2>
            <div class="col-md-3"
            v-for="gOne in gridOne"
            :key="gOne.title">
                <h3 class="text-center">{{gOne.title}}</h3>
                <p>{{gOne.body}}</p>
            </div>
        </div>
        
        <div class="row bg-info">
            <h2>{{headerTwo}}</h2>
            <div :class="gTwo.class"
                v-for="gTwo in gridTwo"
                :key="gTwo.title">
                <h3 class="text-center">{{gTwo.title}}</h3>
                <p>{{gTwo.body}}</p>
            </div>
        </div>
        
        <div class="row bg-warning">
            <h2>{{headerThree}}</h2>
            <div :class="gThree.class"
                v-for="gThree in gridThree"
                :key="gThree.title">
                <h3 class="text-center">{{gThree.title}}</h3>
                <p>{{gThree.body}}</p>
            </div>
        </div>
    </main>
</template>

<style scoped>
    h2 {
        color:green;
    }
</style>