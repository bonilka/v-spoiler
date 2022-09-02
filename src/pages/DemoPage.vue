<template>
    <div class="hello">
        <img alt="Vue logo" src="../assets/logo.png" />
        <h1 class="text-center">Vue Spoiler</h1>
        <h2>Introduction</h2>
        <p>
            Vue Spoiler is simple component for showing and hiding content. It
            could be useful for build accordions, or to hiding long agreements.
        </p>
        <p>
            Component based on slot body height and give possibility to trigger
            toggling content visibility by your way.
        </p>
        <h2>Content</h2>
        <nav class="nav">
            <ul>
                <li>
                    <a href="#start">Get started</a>
                </li>
                <li>
                    <a href="#props">Props</a>
                </li>
                <li>
                    <a href="#events">Events</a>
                </li>
                <li>
                    <a href="#examples">Examples</a>
                </li>
            </ul>
        </nav>
        <h2 id="props">Props</h2>
        <h2 id="events">Events</h2>
        <h2 id="examples">Examples</h2>
        <h3>Spoiler action by button</h3>
        <ButtonStory />
        <h3>Accordion implementation</h3>
        <AccordionStory />
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import ButtonStory from "../stories/ButtonStory.vue";
import AccordionStory from "../stories/AccordionStory.vue";


export default defineComponent({
    name: "DemoPage",
    components: {
        ButtonStory,
        AccordionStory
    }
});
</script>

<style scoped>
h1 {
    font-weight: 400;
}

img {
    display: block;
    margin: auto;
}
a {
    color: #42b983;
}

nav {
}
</style>
