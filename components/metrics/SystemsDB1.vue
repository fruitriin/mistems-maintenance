<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "SystemsDB1",
});
</script>

<template>
  <div>DB(Primary)</div>
  <div style="display: flex; flex-wrap: wrap">
    <div>
      ロードアベレージ<br />
      <iframe
        src="https://mackerel.io/embed/public/embed/KJr1eCcRLckSZuM4t5o1SgYDNeQiEducJapC8NyhetYI95kjZcgxxpUu9MhFiJp7?period=30m"
        height="200"
        width="400"
        frameborder="0"
      />
    </div>
    <div>
      CPU<br />
      <iframe
        src="https://mackerel.io/embed/public/embed/ss6mXWd9cMgF07ShCXvdXFunSYgD6HUA8NyHrT2B8LBv8RDB4XzXhQtRhZcDjmks?period=30m"
        height="200"
        width="400"
        frameborder="0"
      />
    </div>
    <div>
      メモリ<br />
      <iframe
        src="https://mackerel.io/embed/public/embed/iqdJcwtGaU5MxeUOBZM6hVZJElHdsn83RNJZLQwws32ThJGVZtfyHlYtBDQgvDGx?period=30m"
        height="200"
        width="400"
        frameborder="0"
      />
    </div>
    <div>
      Disk<br />
      <iframe
        src="https://mackerel.io/embed/public/embed/9NEKqlxWUUIb6SYRAKoOHqMJyYxiQlLHjMYbPu27anTy8OU75SpjhZWDP5fpyyvR?period=30m"
        height="200"
        width="400"
        frameborder="0"
      />
    </div>
    <div>
      IO<br />
      <iframe
        src="https://mackerel.io/embed/public/embed/Xtk3h1iblRGNmq1leMc0BQIRQ5gWDCMSoRnlGLJsp30IcX4WVO6PbB0rODy04cKU?period=30m"
        height="200"
        width="400"
        frameborder="0"
      />
    </div>
  </div>
</template>

<style scoped lang="scss"></style>
