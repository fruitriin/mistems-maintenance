<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: ["title", "url", "凡例"],
  data() {
    return {
      toggle解説: false,
    };
  },
});
</script>

<template>
  <div style="width: min-content; padding: 0.5rem">
    <h3>{{ title }}</h3>

    <ul style="display: flex; flex-wrap: wrap">
      <li
        v-for="例 in 凡例"
        :key="例.text"
        :style="`color:${例.color}; padding-right: 1.5rem`"
      >
        {{ 例.text }}
      </li>
    </ul>
    <iframe :src="url" height="200" width="400" frameborder="0" />
    <div style="width: fit-content">
      <button @click="toggle解説 = !toggle解説">+</button>数値の意味
      <p v-if="toggle解説">
        <slot name="解説" />
      </p>
    </div>
  </div>
</template>
