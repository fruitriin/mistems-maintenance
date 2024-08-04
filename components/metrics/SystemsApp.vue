<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "SystemsApp",
});
</script>

<template>
  <div>Misskey(App)</div>
  <div style="display: flex; flex-wrap: wrap">
    <div class="item">
      ロードアベレージ<br />
      <iframe
        src="https://mackerel.io/embed/public/embed/zDhYnIFK8HaOF8XjzPw5mWhrb4QJTFpj5UhNdoIMiBB04IJcEisyNdBRXdKJ2fq1?period=30m"
        height="200"
        width="400"
        frameborder="0"
      />
    </div>
    <div class="item">
      CPU<br />
      <iframe
        src="https://mackerel.io/embed/public/embed/EA0rfRa2rfdRVbQ7DISMyAjGMCtU36l84tdOerjrM5t13ydZiARjh1iuze6QxEAr?period=30m"
        height="200"
        width="400"
        frameborder="0"
      />
    </div>
    <div class="item">
      メモリー<br />
      <iframe
        src="https://mackerel.io/embed/public/embed/iqmXxYziC63FR1XX7mZUOjR1KzGsRwNnTXHGpzUj7PmschRVIek6VPt6FrbZkB9R?period=30m"
        height="200"
        width="400"
        frameborder="0"
      />
    </div>
    <div class="item">
      Disk<br />
      <iframe
        src="https://mackerel.io/embed/public/embed/Vup7uXZC6PtSia2kv4rnOti2weHt6i4qckjSavZdPBk2sMBcxvyJtXTILFoxAoDq?period=30m"
        height="200"
        width="400"
        frameborder="0"
      ></iframe>
    </div>
    <div class="item">
      IO<br />
      <iframe
        src="https://mackerel.io/embed/public/embed/x7at7iB6tpbxul9DlhvYOiL63MZUa3TJVjREn390BSKdma05weDmTv2j1wlYEf0U?period=30m"
        height="200"
        width="400"
        frameborder="0"
      ></iframe>
    </div>
  </div>
</template>

<style scoped lang="scss"></style>
