<template>
<div class="story stroy--button">
    <button
        class="button"
        @click="values = !values"
        >
        Toggle
    </button>
    <spoiler v-model="values">
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
import Spoiler from "../components/Spoiler.vue";

export default defineComponent({

    components: {
      Spoiler
    },
    data() {
        return {
            values: false
        };
    }
});
</script>

<style scoped>

</style>
