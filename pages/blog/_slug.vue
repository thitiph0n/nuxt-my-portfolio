<template>
  <dir>
    <div class="container">
      <section class="cover">
        <b-image
          :src="require(`@/assets/blogs-cover/${post.cover}`)"
          alt="blogs cover image"
          ratio="16by5"
        ></b-image>
      </section>
      <article class="content mt-5">
        <h1 class="title is-size-2">{{ post.title }}</h1>
        <p class="subtitle">{{ post.author }} | {{ post.updatedAt }}</p>
        <br />
        <nuxt-content :document="post" />
      </article>
    </div>
  </dir>
</template>
<script>
import moment from "moment";

export default {
  async asyncData({ $content, params }) {
    const post = await $content("blogs", params.slug).fetch();

    if (post.updatedAt) {
      post.updatedAt = moment(post.updatedAt).format("MMMM Do YYYY");
    }

    return {
      post
    };
  }
};
</script>

<style scoped></style>
