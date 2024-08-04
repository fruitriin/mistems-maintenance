<script lang="ts">
import { defineComponent } from "vue";
import SystemsDB1 from "~/components/metrics/SystemsDB1.vue";
import SystemsApp from "~/components/metrics/SystemsApp.vue";

export default defineComponent({
  name: "metrics",
  components: { SystemsDB1, SystemsApp },
});
</script>

<template>
  <SystemsApp />
  <SystemsDB1 />
</template>

<style scoped lang="scss"></style>
