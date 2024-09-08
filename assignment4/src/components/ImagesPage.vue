<script setup>

import { ref } from "vue";
const name = ref("ImagesPage");

/* create array of Landscape images to call on in template*/
const images = ref([
    {
        src: 'https://live.staticflickr.com/65535/51537246564_4d6e3ea0fd_b.jpg',
        alt: 'Mountain and waterfall in iceland',
        title: 'Kirkjufell, Iceland',
        class: 'img-fluid w-75 p-2 d-block mx-auto img'
    },
    {
        src: 'https://live.staticflickr.com/65535/51889963733_163ddcbf60_b.jpg',
        alt: 'mountais and forest reflected in lake',
        title: 'Glacier National Park, Montana USA',
        class: 'img-fluid w-75 p-2 d-block mx-auto img'
    },
    {
        src: 'https://images.pexels.com/photos/1166209/pexels-photo-1166209.jpeg',
        alt: 'lavender fields',
        title: 'Lavender Field, France',
        class: 'img-fluid w-75 p-2 d-block mx-auto img'
    },
    {
        src: 'https://images.pexels.com/photos/1933239/pexels-photo-1933239.jpeg',
        alt: 'northern lights over the mountains',
        title: 'Northern Lights, Norway',
        class: 'img-fluid w-75 p-2 d-block mx-auto img'
    },
    {
        src: 'https://images.pexels.com/photos/632522/pexels-photo-632522.jpeg',
        alt: 'cliff side city in italy',
        title: 'Camogli, Italy',
        class: 'img-fluid w-75 p-2 d-block mx-auto img'
    },    
    {
        src:'https://images.pexels.com/photos/2437296/pexels-photo-2437296.jpeg',
        alt: 'building on lake infront of mountain',
        title: 'Lake Misurina, Italy',
        class: 'img-fluid w-75 p-2 d-block mx-auto img'
    },
    {
        src: 'https://images.pexels.com/photos/1955134/pexels-photo-1955134.jpeg',
        alt: 'a long open road',
        title: 'Road in Iceland',
        class: 'img-fluid w-75 p-2 d-block mx-auto img'
    },
    {
        src: 'https://images.pexels.com/photos/3648269/pexels-photo-3648269.jpeg',
        alt: 'rio from high viewpoint',
        title: 'Rio de Janeiro, Brazil',
        class: 'img-fluid w-75 p-2 d-block mx-auto img'
    },
    ],);


/* create array of B/W images to call on in template*/
 const imagesCarousel = ref([
    {
        class: 'carousel-item active',
        src: 'https://images.pexels.com/photos/1529881/pexels-photo-1529881.jpeg',
        alt: 'forest in black and white',
        title: 'title'
    },
    {
        class: 'carousel-item',
        src: 'https://images.pexels.com/photos/763097/pexels-photo-763097.jpeg',
        alt: 'mountains in black and white',
        title: 'title'
    },
    {
        class: 'carousel-item',
        src: 'https://images.pexels.com/photos/276374/pexels-photo-276374.jpeg',
        alt: 'mountains and lake in black and white',
        title: 'title'
    },
 ],);


//Image Prop Component
import ImageList from './ImageList.vue'; 

/* function borderToggle () {
    let image = document.querySelector('.img-sel')
    console.log('image selected');
    image.style.border = "solid black";
} */

function useBorderFunc(index) {
    console.log(index);
}

</script>


<template>
   <main>
        <div class="container mt-5 d-flex flex-wrap gap-2 justify-content-center">
        <!-- 
            Name the props we are passing down to Image List from the specified array
            use v-for to loop through the array and display each object (dynamic props)
         -->
         <ImageList 
                 v-for="(image, index) in images"
                 :key='image.src'
                 :src='image.src' 
                 :alt='image.alt'
                 :title='image.title'
                 :class='image.class'
                 :index="index"
                 v-on:click="useBorderFunc(index)"
            >
         </ImageList>
            
        </div>
        <div id="myFirstCarousel" class="carousel slide container mt-5 mb-5 w-75">
                <div class="carousel-inner">
                  <!--create image carousel 
                  use v-for to loop thrue imagesCarousel array
                  use imageC.class to make sure the first image of the array has 'active' while the following images don't
                  use ImageList prop to get imagesCarousel properties-->
                    <img
                    v-for='imageC in imagesCarousel' 
                    :key='imageC.src'
                    :src='imageC.src' 
                    :alt='imageC.alt'
                    :title='imageC.title'
                    :class='imageC.class'
                    >
                </div>
                <!-- use buttons to move thru the image carousel-->
                <button class="carousel-control-prev" 
                        type="button" 
                        data-bs-target="#myFirstCarousel" 
                        data-bs-slide="prev"
                        >
                  <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                  <span class="visually-hidden">Previous</span>
                </button>
                <button class="carousel-control-next" 
                        type="button" 
                        data-bs-target="#myFirstCarousel" 
                        data-bs-slide="next"
                        >
                  <span class="carousel-control-next-icon" aria-hidden="true"></span>
                  <span class="visually-hidden">Next</span>
                </button>
        </div>
   </main>

   
</template>

<style scoped>

</style>