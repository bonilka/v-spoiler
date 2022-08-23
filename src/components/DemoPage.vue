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
        <button
            class="button"
            @click="button_model = !button_model"
            >
            Toggle
        </button>
        <spoiler v-model="button_model">
            <div class="content-box">
                Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                Maxime sapiente natus, iusto culpa aspernatur sed ea modi voluptatibus doloribus.
                Quaerat recusandae quia fuga hic quasi impedit, accusamus tempore, possimus porro,
                eligendi soluta delectus temporibus ab sed ad aperiam quam voluptates molestiae quo magni odio eum odit?
                Excepturi asperiores ullam sequi!
            </div>
        </spoiler>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Spoiler from "./Spoiler.vue";

export default defineComponent({

    name: "HelloWorld",
    components: {
      Spoiler
    },
    props: {
        msg: String,
    },
    data() {
        return {
            button_model: false
        }
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
