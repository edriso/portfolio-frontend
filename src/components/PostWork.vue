<template>
  <div class="post">
    <a
      class="post__link"
      :href="post.link"
      target="_blank"
      rel="noopener noreferrer"
    >
      <img
        class="post__img"
        :src="imageSrc(post.img)"
        :alt="post.title"
        decoding="async"
      />
      <p class="post__title" v-if="post.title">{{ post.title }}</p>
    </a>

    <div class="post__body flex flex-jc-sb flex-ai-c flex-gap-md">
      <ul class="post__tags flex flex-gap-sm">
        <li v-for="tag in post.tags" :key="tag">
          <router-link
            :to="{ name: 'tag', params: { tag: tag.toLowerCase() } }"
          >
            #{{ tag }}
          </router-link>
        </li>
      </ul>

      <!-- <p class="post__date">{{ post.date }}</p> -->
    </div>
  </div>
</template>

<script>
export default {
  setup() {
    const imageSrc = (imgName) => {
      return new URL(`../assets/works/${imgName}`, import.meta.url).href;
    };
    return { imageSrc };
  },
  props: {
    post: Object,
  },
};
</script>
