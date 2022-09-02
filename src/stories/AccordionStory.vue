<template>
<div class="story stroy--button">
    <div class="accordion">
        <div
        v-for="item in list"
        :key="item.id"
        class="accordion-item"
        @click="onClick(item)"
        >
            <div class="accordion-item__title">
                <span :class="['accordion-item__arrow', {'accordion-item__arrow--opened': item.opened}]" />
                {{item.title}}
            </div>
        <spoiler v-model="item.opened">
            <div class="content-box">
                Lorem ipsum, dolor sit amet consectetur adipisicing elit.
                Maxime sapiente natus, iusto culpa aspernatur sed ea modi voluptatibus doloribus.
                Quaerat recusandae quia fuga hic quasi impedit, accusamus tempore, possimus porro,
                eligendi soluta delectus temporibus ab sed ad aperiam quam voluptates molestiae quo magni odio eum odit?
                Excepturi asperiores ullam sequi!
            </div>
        </spoiler>
        </div>
    </div>
</div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Spoiler from "../components/Spoiler.vue";
interface IAccorionItem {
    id: number;
    opened: boolean;
    title: string;
    text: string;
}

export default defineComponent({
    components: {
      Spoiler
    },
    data() {
        return {
            values: 1,
            list: [
                {
                    id: 1,
                    opened: false,
                    title: 'Lorem ipsum',
                    text: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Voluptas laboriosam ipsum consectetur praesentium expedita doloribus debitis tempore mollitia saepe cumque.'
                },
                {
                    id: 2,
                    opened: false,
                    title: 'Hic, fugit',
                    text: 'Hic, fugit. Sed illum, modi, odio veritatis nobis laudantium quod dolores doloremque itaque accusantium neque temporibus expedita velit ab quae.'
                },
                {
                    id: 3,
                    opened: false,
                    title: 'Deleniti laborum',
                    text: 'Deleniti laborum excepturi nobis repellendus et culpa dolorem nulla, similique corporis saepe natus nisi laudantium aliquid ab assumenda, minima aperiam.'
                },
                {
                    id: 4,
                    opened: false,
                    title: 'Optio culpa',
                    text: 'Optio culpa aperiam illo molestiae earum sapiente, placeat, quidem, veniam odit nulla eaque vel aspernatur sed? Dolorum esse accusamus excepturi.'
                },
            ] as IAccorionItem[]
        };
    },
    methods: {
        onClick({id}: IAccorionItem) {
            this.list.forEach((item) => (item.opened = (id === item.id && !item.opened)));
        }
    }
});
</script>

<style scoped>
.accordion {
    display: block;
}

.accordion-item__title {
    padding: 8px 4px;
    font-weight: 600;
    border-bottom: 1px solid var(--color-border);
    cursor: pointer;
}

.accordion-item__arrow {
    display: inline-block;
    margin-right: 12px;
    width: 0;
    height: 0;
    border-left: 6px solid transparent;
    border-right: 6px solid transparent;
    border-top: 10px solid currentColor;
    transition: transform 0.1s;
}

.accordion-item__arrow--opened {
    transform: scaleY(-1);
}
</style>
