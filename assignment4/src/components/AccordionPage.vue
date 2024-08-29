<script setup>
import { ref } from "vue";

const name = ref("AccordionPage");

const accordion = ref([
    {
        header: `Accordion #1`,
        target: `#collapseOne`,
        controls: `collapseOne`,
        id: `collapseOne`,
        body: `Lorem ipsum dolor sit amet consectetur, adipisicing elit. Totam voluptatem provident tempore ducimus 
                      quidem facere magnam similique quaerat nihil molestias?`
    },
    {
        header: `Accordion #2`,
        target: `#collapseTwo`,
        controls: `collapseTwo`,
        id: `collapseTwo`,
        body: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Et, quae quis culpa itaque ipsa debitis, 
                      rerum expedita eaque quas, voluptatem velit quibusdam! Maxime, id libero? Repudiandae minus sequi optio consectetur!`
    },
    {
        header: `Accordion #3`,
        target: `#collapseThree`,
        controls: `collapseThree`,
        id: `collapseThree`,
        body: `Lorem ipsum, dolor sit amet consectetur adipisicing elit. Magni, minima aspernatur! Tenetur sapiente eos 
                      incidunt, vel debitis eligendi quam dolor dicta aliquid a ut similique odio esse culpa! Nisi consequuntur 
                      nihil distinctio fugit, expedita consequatur! Hic asperiores dolor porro quis!`
    },
],); 
const show = ref(true)
</script>

<template>
    <main>
        <div 
        v-for="a in accordion"
        :key="a.header"
        class="accordion" id="myFirstAccordion"
        >
            <div class="accordion-item">
                <h2 class="accordion-header">{{a.header}}</h2>    
                <button
                    class="accordion-button collapsed"
                    type="button" 
                    data-bs-toggle="collapse"
                    aria-expanded="false" 
                    :data-bs-target="a.target"
                    :aria-controls="a.controls"
                    @click= "show"
                >
                </button>
                <div :id="a.id" class="accordion-collapse collapse" data-bs-parent="#myFirstAccordion">
                    <div v-show="show" class="accordion-body">
                        {{a.body}}
                    </div>
                </div>
            </div>
        </div>
    </main>
    
</template>

<style scoped>
h2 {
    color:green;
}
</style>