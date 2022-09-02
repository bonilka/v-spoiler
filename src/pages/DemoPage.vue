<template>
    <div class="demo-page">
        <picture class="demo-page__logo">
            <img
                alt="Vue Spoiler logo"
                class="demo-page__logo-origin"
                src="../assets/logo.png"
                />
            <img
                alt="Vue Spoiler logo"
                :class="['demo-page__logo-inverse', {'demo-page__logo-inverse--shown': isThemeInverse}]"
                src="../assets/logo--inverse.png"
                />
        </picture>
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
            <table>
                <th>Name</th>
                <th>Type</th>
                <th>Description</th>
                <tbody>
                    <tr>
                        <td>
                            modelValue
                        </td>
                        <td>
                            Boolean
                        </td>
                        <td>
                            Provide value to opening / closing
                        </td>
                    </tr>
                    <tr>
                        <td>
                            time
                        </td>
                        <td>
                            Number
                        </td>
                        <td>
                            Duration time for animation (ms)
                        </td>
                    </tr>
                </tbody>
            </table>
        <h2 id="events">Events</h2>
        <table>
                <th>Name</th>
                <th>Payload</th>
                <tbody>
                    <tr>
                        <td>
                            open-completed
                        </td>
                        <td>
                            Triggers on animation of opening ended
                        </td>
                    </tr>
                    <tr>
                        <td>
                            close-completed
                        </td>
                        <td>
                            Triggers on animation of closing ended
                        </td>
                    </tr>
                </tbody>
            </table>
        <h2 id="examples">Examples</h2>
        <h3>Spoiler action by button</h3>
        <ButtonStory />
        <h3>Accordion implementation</h3>
        <AccordionStory />
        <footer class="demo-page__footer" />
        <GithubIco class="demo-page__github"/>
    </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ButtonStory from "../stories/ButtonStory.vue";
import AccordionStory from "../stories/AccordionStory.vue";
import GithubIco from "../components/GithubIco.vue";

export default defineComponent({
    name: "DemoPage",
    components: {
        ButtonStory,
        AccordionStory,
        GithubIco,
    },
    inject: ['isThemeInverse']
});
</script>

<style scoped>
.demo-page__logo {
    display: block;
    position: relative;
    margin: auto;
    max-width: 250px;
}

.demo-page__logo-origin {
    display: block;
    width: 100%;
}

.demo-page__logo-inverse {
    display: block;
    position: absolute;
    top: 0;
    width: 100%;
    opacity: 0;
    transition: opacity 0.15s;
}

.demo-page__logo-inverse--shown {
    opacity: 1;
}

.demo-page {
    padding: 24px;
}

.demo-page__footer {
    padding: 64px 0 0 0;
    text-align: center;
    font-size: 14px;
}

.demo-page__github {
    position: absolute;
    top: 0;
    right: 0;
}
</style>
