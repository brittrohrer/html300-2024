<script setup>
import { ref } from "vue";

const name = ref("ImagesPage");
 //have to usev-bind for a link

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
            <img class="img-fluid w-50 object-fit-contain"
                v-for="imageP in imagesPortrait"
                :key="imageP.link"
                :src="imageP.link"
                :alt="imageP.text">
        </div>
   </main>

   
</template>

<style scoped>
h2 {
    color:green;
}
</style>