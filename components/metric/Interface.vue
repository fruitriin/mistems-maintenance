<script lang="ts">
export default {
  props: ["url"],
};
</script>

<template>
  <metricTemplate
    title="Interface"
    :url="url"
    :凡例="[
      { text: 'enp1s0 rxBytes', color: '#ad9173' },
      { text: 'enp1s0 txBytes', color: '#435faf' },
    ]"
  >
    <template #解説>
      ネットワーク帯域の使用状況です。単位はKB/秒、txは送信、rxは受信。
      この値が高いところをキープしていると、ネットワークのボトルネックになっている可能性がある。
    </template>
  </metricTemplate>
</template>
