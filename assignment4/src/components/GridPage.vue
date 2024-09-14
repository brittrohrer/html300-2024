<script setup>

import { ref } from "vue";
const name = ref("GridPage");

/* Create array and header variable to dynamically build page content for each grid container */
const headerOne =ref("Aperture")
const gridOne = ref([
    {
        class: `col-lg-6`,
        title: `What is Aperture?`,
        body: `The aperture controls the area which allows light to pass through the camera lense.
                The aperture setting determines a photos depth of field which is the range in which
                the object in the photo appear in focus. It is expresed in terms of f-stop. `
    },
    {
        class: `col-lg-3 text-center`,
        title: `Wide Aperture`,
        body: `This is when a low f-stop is used. It creates a shallow depth of field. It is great for 
                portrait photography where the subject/person is in focus while the background is out of focus.`
    },
    {
        class: `col-lg-3 text-center`,
        title: `Narrow Aperture`,
        body: `This is when a high f-stop is used and creates a large depth of field. It is ideal for landscape phtography 
        where more of the entire image is in focus.`               
    },
],);
const headerTwo = ref("Shutter Speed")
const gridTwo = ref([
    {
        class: `col-lg-6`,
        title: `What is Shutter Speed`,
        body: `The camera's shutter determines when the camera's senser will be open to 
        incoming light. So the shutter speed refers to how long the light is allowed to enter
        thru the camera lense.`
    },
    {
        class: `col-lg-3 text-center`,
        title: `Slow Shutter`,
        body: ` This will create more image blur. This is best used with a tripod to prevent hand shaking from
        being captured. Great for capturing images of the night sky when more time is needed to capture the light. This
        is also used for creative touches when photographing moving water like a waterfall to give nice blurred water. 
        Speeds for these types of images could include 1/30"-20" or sometimes longer.`
    },
    {
        class: `col-lg-3 text-center`,
        title: `Fast Shutter`,
        body: `This will create sharper images but also allow less light in.
        Great for photographing wildlife or even sporting events where the subject is moving at higher speeds.`               
    },
],);
const headerThree = ref("ISO")
const gridThree = ref([
    {
        class: `col-sm-6`,
        title: `What is ISO?`,
        body: `It determines how sensitive the camera is to the light entering it.`
    },
    {
        class: `col-sm-6`,
        title: `Why do we care?`,
        body: `A lower ISO is almost always the preferred way. This is becasuse a higher ISO can increase 
        the amount of image noise.`
    },
],);
</script>

<template>
    <main class="container">
        <!-- use a v-for for each grid section to display the header, title and body with each of their specified layouts-->
        <div class="row bg-primary">
            <h2>{{headerOne}}</h2>
            <div :class="gOne.class"
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
h2,h3,p {
    color: black;
}
</style>