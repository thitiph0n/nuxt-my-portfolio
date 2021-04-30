<template>
  <div class="container">
    <section class="hero">
      <div class="hero-body has-text-centered">
        <p class="title is-size-2">
          My Blog
        </p>
        <p class="subtitle">
          Lorem, ipsum dolor sit amet consectetur adipisicing elit.
        </p>
      </div>
    </section>
    <section class="columns is-multiline is-variable is-4">
      <div v-for="post in posts" :key="post.slug" class="column is-one-third">
        <div class="card">
          <nuxt-link :to="`/blog/${post.slug}`">
            <div class="card-image">
              <b-image
                :src="require(`@/assets/blogs-cover/${post.cover}`)"
                alt="blogs cover image"
                ratio="16by6"
              ></b-image>
            </div>
            <div class="card-content">
              <div class="content">
                <h4>{{ post.title }}</h4>
                <p>
                  {{ post.description }}
                </p>
                <p>{{ post.author }} | {{ post.updatedAt }}</p>
              </div>
            </div>
          </nuxt-link>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import moment from "moment";

export default {
  async asyncData({ $content }) {
    const posts = await $content("blogs")
      .without(["body"])
      .fetch();

    posts.forEach(post => {
      if (post.updatedAt) {
        post.updatedAt = moment(post.updatedAt).format("MMMM Do YYYY");
      }
    });

    return {
      posts
    };
  }
};
</script>
