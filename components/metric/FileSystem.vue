<script lang="ts">
export default {
  props: ["url"],
};
</script>

<template>
  <metricTemplate
    title="FileSystem"
    :url="url"
    :凡例="[
      { text: 'used', color: '#72c8d6' },
      { text: 'size', color: '#e8b646' },
    ]"
  >
    <template #解説>
      ディスクサイズとその使用量を表すメトリック。usedが溢れていなければ大丈夫。
    </template>
  </metricTemplate>
</template>
