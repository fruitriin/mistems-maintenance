<script lang="ts">
export default {
  props: ["url"],
};
</script>

<template>
  <metricTemplate
    title="ロードアベレージ"
    :url="url"
    :凡例="[
      { text: 'loadavg1', color: '#72c8d6' },
      { text: 'loadavg5', color: '#e8b646' },
      { text: 'loadavg15', color: '#ab85c1' },
    ]"
  >
    <template #解説>
      １CPUに対して、平均的にどれだけプロセスが実行待ちになっているか。それぞれ1分前、5分前、15分前の平均値。CPUコア数の数値以下であれば正常。
    </template>
  </metricTemplate>
</template>
