<template>
  <main class="tag">
    <p class="selected text-center mb-md">#{{ tag }}</p>

    <div class="posts-grid" v-if="posts.length">
      <Post v-for="post in posts" :key="post.id" :post="post" />
    </div>
  </main>
</template>

<script>
import Post from "../components/PostWork.vue";
import axios from "axios";
import { ref, onMounted, watchEffect } from "@vue/runtime-core";

export default {
  name: "Tag",
  components: { Post },
  props: ["tag"],
  setup(props) {
    const allPosts = ref([]);
    const posts = ref([]);

    onMounted(() => {
      axios.get("../db/works.json").then((res) => {
        allPosts.value = res.data.slice().reverse();
      });
    });

    watchEffect(() => {
      posts.value = allPosts.value.filter((post) => {
        return post.tags.find((tag) => tag.toLowerCase() === props.tag);
      });

      if (posts.value.length) {
        return posts.value;
      }
    });

    return { posts };
  },
};
</script>
