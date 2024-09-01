<script setup>
import { ref } from "vue";

const name = ref("Home");

const touchButton = ref(true);


/* Jumbotron
created ref variables for this so that in the template section the content could be rendered dynamically
and be changed easily if the text changed*/
const jumboTitle = ref(`Jumbotron Title`);
const jumboText = ref(` This is the first jumbotron text!!!!!!!!!!!!!                                
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusantium debitis facere, 
                        vitae in iste beatae quidem repudiandae optio dignissimos eos cupiditate suscipit 
                        explicabo nihil atque et molestias, ratione maxime repellat eaque exercitationem quaerat 
                        ipsa similique excepturi voluptatibus. Quibusdam placeat blanditiis sunt modi quas recusandae, 
                        saepe laboriosam ea facilis. Pariatur reiciendis beatae quod atque quas inventore unde assumenda 
                        debitis incidunt itaque.`);
const jumboText2 = ref(` This is the Second jumbotron text!!!!!!!!!!!!!                                
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusantium debitis facere, 
                        vitae in iste beatae quidem repudiandae optio dignissimos eos cupiditate suscipit 
                        explicabo nihil atque et molestias, ratione maxime repellat eaque exercitationem quaerat.`);       


/* Cards
create array of cards objects to call on in the template section*/
const cards = ref([
                {
                    header: `Title 1`,
                    text: `Lorem ipsum dolor, sit amet consectetur adipisicing elit. Modi, debitis.`,
                    link: `"#"`,
                    button: `Link Button`
                },
                {
                    header: `Title 2`,
                    text: `Lorem ipsum dolor, sit amet consectetur adipisicing elit. Modi, debitis.`,
                    link: `"#"`,
                    button: `Link Button`
                },
                {
                    header: `Title 3`,
                    text: `Lorem ipsum dolor, sit amet consectetur adipisicing elit. Modi, debitis.`,
                    link: `"#"`,
                    button: `Link Button`
                },
                {
                    header: `Title 3`,
                    text: `Lorem ipsum dolor, sit amet consectetur adipisicing elit. Modi, debitis.`,
                    link: `"#"`,
                    button: `Link Button`
                },
            ],
);

</script>

<template>
    <main class="container">
        <div class="jumbotron jumbotron-fluid bg-info">
                <!--create jumbotron -->
                <div class="container mt-5 p-2">
                    <!-- call the jumbotron title from the script section -->
                    <h2 class="display-4">{{jumboTitle}}</h2>
                    <!--create top margin of 2 text and emphasize text with "lead"
                    also create a button and clickevent that use if/else that will use the state of the button when clicked (true or false) 
                    to determine with text to display-->
                    <button class="btn btn-danger" @click="touchButton = !touchButton">Click Me!</button>
                    <p v-if ="touchButton" class="lead mt-2">{{jumboText}}</p>
                    <p v-else class="lead mt-2">{{jumboText2}}</p>
                </div>
            </div>
        <div class= "container d-flex flex-row justify-content-evenly mt-5 mb-5 flex-wrap gap-3">
            <!-- use a vue for loop to loop thru the cards array in script section to create each card-->
            <div class="card" 
                style="width: 18rem;" 
                v-for="card in cards" :key="card.name">
                <div class="card-body">
                    <h3 class="card-title">
                    {{card.header}}</h3>
                    <p class="card-text">{{card.text}}</p>
                    <!-- bind the card link so the link can function properly-->
                    <a :href="card.link" 
                        class="btn btn-primary">
                        {{card.button}}</a>
                </div>
            </div>
        </div>
    </main>
    
</template>

<style scoped>
    p, h2 {
        color: black;
    }
    .toggle-button {
        margin-top: 2rem;
    }
</style>