<template>
  <div
    class="app"
    style="display: flex; flex-direction: column; overflow: hidden"
  >
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
            {{ chat.message }}
          </li>
        </ul>
      </div>
    </div>
    <iframe
      src="https://status.misskey.systems/"
      width="100%"
      height="100%"
    ></iframe>
  </div>
</template>

<style>
html,
body,
#__nuxt,
.app {
  height: 100%;
}
</style>
<script lang="ts">
import { createClient, SupabaseClient } from "@supabase/supabase-js";

const supabaseUrl = "https://pountivqclwqpqkhavtn.supabase.co";
const supabase = createClient(
  supabaseUrl,
  "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6InBvdW50aXZxY2x3cXBxa2hhdnRuIiwicm9sZSI6ImFub24iLCJpYXQiOjE3MDU3NDUwMjcsImV4cCI6MjAyMTMyMTAyN30.gqUimyPjYrILDl6VEtRHotdMvH_ZF0ldW0xpDHUmA8w",
);

// Create a function to handle inserts
export default defineNuxtComponent({
  data() {
    return {
      chats: [] as { id: number; message: string }[],
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
