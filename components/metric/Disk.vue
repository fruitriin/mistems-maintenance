<script lang="ts">
export default {
  props: ["url"],
};
</script>

<template>
  <metricTemplate
    title="Disk"
    :url="url"
    :凡例="[
      { text: 'vda reads', color: '#cfc400' },
      { text: 'vda writes', color: '#689261' },
      { text: 'vda1 reads', color: '#ea7894' },
      { text: 'vda1 writes', color: '#288fce' },
    ]"
  >
    <template #解説>
      一秒あたりのディスクへのアクセス頻度。高すぎるとiowaitの原因になる
    </template>
  </metricTemplate>
</template>
