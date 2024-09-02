<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({});
</script>

<template>
  <h2>Misskey Database(Primary)</h2>
  <div style="display: flex; flex-wrap: wrap">
    <MetricLoadAvg
      url="https://mackerel.io/embed/public/embed/KJr1eCcRLckSZuM4t5o1SgYDNeQiEducJapC8NyhetYI95kjZcgxxpUu9MhFiJp7?period=23h46m"
    />
    <MetricCPU
      url="https://mackerel.io/embed/public/embed/ss6mXWd9cMgF07ShCXvdXFunSYgD6HUA8NyHrT2B8LBv8RDB4XzXhQtRhZcDjmks?period=23h46m"
    />
    <MetricMemory
      url="https://mackerel.io/embed/public/embed/iqdJcwtGaU5MxeUOBZM6hVZJElHdsn83RNJZLQwws32ThJGVZtfyHlYtBDQgvDGx?period=23h46m"
    />
    <MetricDisk
      url="https://mackerel.io/embed/public/embed/9NEKqlxWUUIb6SYRAKoOHqMJyYxiQlLHjMYbPu27anTy8OU75SpjhZWDP5fpyyvR?period=23h46m"
    />
    <MetricInterface
      url="https://mackerel.io/embed/public/embed/Xtk3h1iblRGNmq1leMc0BQIRQ5gWDCMSoRnlGLJsp30IcX4WVO6PbB0rODy04cKU?period=23h46m"
    />
    <MetricFileSystem
      url="https://mackerel.io/embed/public/embed/RMGN1ZHMiqgsIUzGLQo4fIH2AD7FbOSAdAdNx2cDpLZwunudUo2Qu30v5mpLE705?period=23h46m"
    />
  </div>
</template>

<style scoped></style>
