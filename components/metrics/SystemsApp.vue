<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({});
</script>

<template>
  <h2>Misskey本体</h2>
  <div style="display: flex; flex-wrap: wrap">
    <MetricLoadAvg
      url="https://mackerel.io/embed/public/embed/zDhYnIFK8HaOF8XjzPw5mWhrb4QJTFpj5UhNdoIMiBB04IJcEisyNdBRXdKJ2fq1?period=23h46m"
    />
    <MetricCPU
      url="https://mackerel.io/embed/public/embed/EA0rfRa2rfdRVbQ7DISMyAjGMCtU36l84tdOerjrM5t13ydZiARjh1iuze6QxEAr?period=23h46m"
    />
    <MetricMemory
      url="https://mackerel.io/embed/public/embed/iqmXxYziC63FR1XX7mZUOjR1KzGsRwNnTXHGpzUj7PmschRVIek6VPt6FrbZkB9R?period=23h46m"
    />
    <MetricDisk
      url="https://mackerel.io/embed/public/embed/Vup7uXZC6PtSia2kv4rnOti2weHt6i4qckjSavZdPBk2sMBcxvyJtXTILFoxAoDq?period=23h46m"
    />
    <MetricInterface
      url="https://mackerel.io/embed/public/embed/x7at7iB6tpbxul9DlhvYOiL63MZUa3TJVjREn390BSKdma05weDmTv2j1wlYEf0U?period=23h46m"
    />
    <MetricFileSystem
      url="https://mackerel.io/embed/public/embed/yC9Jg4WA2CXIxrI3cBH9Yl7fI0nTpDJ9QkXFBbyh2DbDJO6yU7htedrvxSRG636u?period=23h46m"
    />
  </div>
</template>

<style scoped></style>
