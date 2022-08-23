<template>
  <div
    :class="class_list"
    :style="{ height: height, '--spoiler-time': `${time}ms` }"
    @transitionend="onTransitionEnd"
    >
    <slot />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import './Spoiler.scss';

export default defineComponent({
  name: 'CSpoiler',
  props: {
    modelValue: {
      type: Boolean,
      default: false,
    },
    time: {
      type: Number,
      default: 150,
    },
  },
  emit: [
    'open-completed',
    'close-completed'
  ],
  data() {
    return {
      height: this.modelValue ? '' : 0,
      is_progress: false,
    };
  },
  computed: {
    class_list(): {[key: string]: boolean} {
      return {
        'c-spoiler': true,
        'c-spoiler--opened': this.modelValue,
        'c-spoiler--closed': !this.modelValue,
        'c-spoiler--open-completed': this.modelValue && !this.is_progress,
        'c-spoiler--close-completed': !this.modelValue && !this.is_progress,
      };
    },
  },
  watch: {
    modelValue(val: boolean) {
      this.height = `${this.$el.scrollHeight}px`;
      this.is_progress = true;

      if (!val) {
        window.requestAnimationFrame(() => {
          this.height = 0;
        });
      }
    },
  },
  methods: {
    onTransitionEnd() {
      if (this.modelValue) {
        this.height = '';
      }
      this.is_progress = false;
      this.$emit(this.modelValue ? 'open-completed' : 'close-completed');
    },
  },
});
</script>