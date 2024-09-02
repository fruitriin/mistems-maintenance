<script lang="ts">
export default {
  props: ["url"],
};
</script>

<template>
  <metricTemplate
    title="メモリ"
    :url="url"
    :凡例="[
      { text: 'used', color: '#72c8d6' },
      { text: 'available', color: '#e8b646' },
      { text: 'total', color: '#ab85c1' },
      { text: 'swap cached', color: '#b3d143' },
      { text: 'swap used', color: '#e59965' },
      { text: 'swap total', color: '#69ccb0' },
    ]"
  >
    <template #解説>
      メモリの使用率。不足しさえしなければたくさん使っているほどお得である。
    </template>
  </metricTemplate>
</template>
