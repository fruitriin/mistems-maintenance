<script lang="ts">
export default {
  props: ["url"],
};
</script>

<template>
  <metricTemplate
    title="CPU"
    :url="url"
    :凡例="[
      { text: 'usr', color: '#72c8d6' },
      { text: 'nice', color: '#e8b646' },
      { text: 'system', color: '#ab85c1' },
      { text: 'irq', color: '#b3d143' },
      { text: 'softirq', color: '#e59965' },
      { text: 'iowait', color: '#69ccb0' },
      { text: 'steal', color: '#ad9173' },
      { text: 'guest', color: '#435fafs' },
      { text: 'idle', color: '#aaa' },
    ]"
  >
    <template #解説>
      サーバー1台のトータルのCPU使用率。<br />
      特に注意が必要なのは以下の４つらしい。<br />
      <ul>
        <li>cpu.user カーネル以外が使用した時間の割合</li>
        <li>cpu.iowait I/O待ちにより、アイドル状態であった時間の割合</li>
        <li>cpu.system カーネルが使用した時間の割合</li>
        <li>cpu.idle I/O待ちがなく、かつCPUがアイドル状態であった時間の割合</li>
      </ul>
      とりあえず溢れていないならたくさん使っているほうがお得である。
    </template>
  </metricTemplate>
</template>
