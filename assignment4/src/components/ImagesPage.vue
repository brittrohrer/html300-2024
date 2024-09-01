<script setup>
import { ref } from "vue";

const name = ref("ImagesPage");

/* create array of Landscape images to call on in template*/
const imagesLandscape = ref([
    {
        link: `https://live.staticflickr.com/65535/51537246564_4d6e3ea0fd_b.jpg`,
        text: `Mountain and waterfall in iceland`
    },
    {
        link: `https://live.staticflickr.com/65535/51889963733_163ddcbf60_b.jpg`,
        text: `mountais and forest reflected in lake`
    },
    {
        link: `https://images.pexels.com/photos/1166209/pexels-photo-1166209.jpeg?auto=compress&cs=tinysrgb&w=1200`,
        text: `lavender fields`
    },
    {
        link: `https://images.pexels.com/photos/1933239/pexels-photo-1933239.jpeg?auto=compress&cs=tinysrgb&w=1200`,
        text: `northern lights over the mountains`
    },
    {
        link: `https://images.pexels.com/photos/632522/pexels-photo-632522.jpeg?auto=compress&cs=tinysrgb&w=1200`,
        text: `cliff side city in italy`
    },      
    ],
 );

/* create array of Portrait images to call on in template*/
 const imagesPortrait = ref([
    {
        link:`https://images.pexels.com/photos/2437296/pexels-photo-2437296.jpeg?auto=compress&cs=tinysrgb&w=1200`,
        text: `building on lake infront of mountain`
    },
    {
        link: `https://images.pexels.com/photos/1955134/pexels-photo-1955134.jpeg?auto=compress&cs=tinysrgb&w=1200`,
        text: `a long open road`
    },
    {
        link: `https://images.pexels.com/photos/3648269/pexels-photo-3648269.jpeg?auto=compress&cs=tinysrgb&w=1200`,
        text: `rio from high viewpoint`
    },
    ],
 );

/* create array of B/W images to call on in template*/
 const imagesCarousel = ref([
    {
        class: `carousel-item active`,
        link: `https://images.pexels.com/photos/1529881/pexels-photo-1529881.jpeg?auto=compress&cs=tinysrgb&w=1200`,
        text: `forest in black and white`
    },
    {
        class: `carousel-item`,
        link: `https://images.pexels.com/photos/763097/pexels-photo-763097.jpeg?auto=compress&cs=tinysrgb&w=1200`,
        text: `mountains in black and white`
    },
    {
        class: `carousel-item`,
        link: `https://images.pexels.com/photos/276374/pexels-photo-276374.jpeg?auto=compress&cs=tinysrgb&w=1200`,
        text: `mountains and lake in black and white`
    },
 ],);
</script>


<template>
   <main>
        <div class="container mt-5 d-flex flex-wrap gap-2 justify-content-center">
            <!-- use a v-for with the binding key to loop thru all the objects in the images array
            use : to bind object in array  to the src and alt text to display images -->
            <img class="img-fluid w-75 p-2 d-block mx-auto" 
                 v-for="imageL in imagesLandscape" 
                 :key="imageL.link"
                 :src="imageL.link" 
                 :alt="imageL.text">       
        </div>
        <div class="container mt-5 d-flex flex-wrap gap-2 justify-content-center">
             <!-- use a v-for with the binding key to loop thru all the objects in the images array
            use : to bind object in array  to the src and alt text to display images -->
            <img class="img-fluid w-50 object-fit-contain"
                v-for="imageP in imagesPortrait"
                :key="imageP.link"
                :src="imageP.link"
                :alt="imageP.text">
        </div>
        <div id="myFirstCarousel" class="carousel slide container mt-5 mb-5 w-75">
                <div class="carousel-inner">
                  <!--create image carousel 
                  use v-for to loop thrue imagesCarousel array
                  use imageC.class to make sure the first image of the array has 'active' while the following images don't-->
                    <div :class="imageC.class"
                        v-for="imageC in imagesCarousel"
                        :key="imageC.link">
                        
                        <img  
                        class="d-block w-100"
                        :src="imageC.link"
                        :alt="imageC.text">
                    </div>
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
h2 {
    color:green;
}
</style>