<template>
  <div class="app" style="display: flex; flex-direction: column">
    <!-- ::CLOUDFLARE_ERROR_500S_BOX:: -->
    <div style="display: flex">
      <div>
        <h1>Mistems is down</h1>

        <a href="https://misskey.systems/"
          >みすてむずは直ってるに違いないときに押すリンク</a
        >
      </div>
      <div style="overflow-y: scroll; width: 100%; height: 200px">
        <form @submit.prevent="submit">
          <input type="text" v-model="text" /><button>おくる</button>
        </form>
        <ul>
          <li v-for="chat in chats" :key="chat.id">
            <span style="display: inline-block; width: 80px">
              {{
                formatDistanceToNow(chat.created_at, {
                  includeSeconds: true,
                  locale: ja(),
                })
              }}
            </span>
            {{ chat.message }}
          </li>
        </ul>
      </div>
    </div>
    <div>
      <button
        @click="tab = 'status'"
        class="tab"
        :class="{ 'tab-active': tab === 'status' }"
      >
        障害状況
      </button>
      <button
        @click="tab = 'metric'"
        class="tab"
        :class="{ 'tab-active': tab === 'metric' }"
      >
        サーバーパフォーマンスモニタ
      </button>
    </div>
    <Status v-if="tab === 'status'" />
    <Metrics v-if="tab === 'metric'" class="metric" />
  </div>
</template>

<style lang="scss">
html,
body,
#__nuxt,
.app {
  height: 100%;
}
.time {
  min-width: 100px;
}

.tab {
  border-radius: 4px;
  padding: 4px 8px;
  &.tab-active {
    background-color: rgb(134, 179, 0);
  }
}
</style>
<script lang="ts">
import { createClient } from "@supabase/supabase-js";
import { formatDistanceToNow } from "date-fns";
import { ja } from "date-fns/locale/ja";
import Status from "~/components/Status.vue";
import Metrics from "~/components/Metrics.vue";

const supabaseUrl = "https://pountivqclwqpqkhavtn.supabase.co";
const supabase = createClient(
  supabaseUrl,
  "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6InBvdW50aXZxY2x3cXBxa2hhdnRuIiwicm9sZSI6ImFub24iLCJpYXQiOjE3MDU3NDUwMjcsImV4cCI6MjAyMTMyMTAyN30.gqUimyPjYrILDl6VEtRHotdMvH_ZF0ldW0xpDHUmA8w"
);

// Create a function to handle inserts
export default defineNuxtComponent({
  components: { Metrics, Status },
  data() {
    return {
      tab: "status" as "status" | "metric",
      chats: [] as { id: number; message: string; created_at: Date }[],
      text: "",
    };
  },
  mounted() {
    this.getChat();
    // Listen to inserts
    setInterval(async () => {
      this.getChat();
    }, 5000);
  },
  methods: {
    ja() {
      return ja;
    },
    formatDistanceToNow,
    async getChat() {
      let { data: todos, error } = await supabase
        .from("todos")
        .select("*")
        .order("id", { ascending: false })
        .range(0, 9);

      if (!todos) return;
      this.chats = todos;
    },
    async submit() {
      const { data, error } = await supabase
        .from("todos")
        .insert([{ message: this.text }]);
      if (error) console.error(error);
      this.text = "";
      this.getChat();
    },
  },
});
</script>
