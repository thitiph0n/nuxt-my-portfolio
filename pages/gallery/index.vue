<template>
  <div>
    <section class="hero ">
      <div class="hero-body">
        <div class="container has-text-centered">
          <p class="title is-1">Gallery</p>
          <p class="subtitle is-4 mt-1">
            “God creates the beauty. My camera and I are a witness.”
          </p>
          <p class="title is-5 mt-1">-Mark Denman</p>
        </div>
      </div>
    </section>
    <section class="columns is-multiline is-variable is-3 px-5">
      <div v-for="photo in photos" :key="photo.id" class="column is-3">
        <div class="box p-0">
          <b-image
            :src="photo.urls.small"
            :alt="photo.alt_description"
            responsive
            lazy
          ></b-image>
        </div>
      </div>
    </section>
    <b-loading v-model="isLoading" :is-full-page="isFullPage">
      <b-icon pack="fas" icon="sync-alt" size="is-large" custom-class="fa-spin">
      </b-icon>
    </b-loading>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios, env }) {
    try {
      const photos = await $axios.$get(
        `https://api.unsplash.com/users/thitiph0n/photos?client_id=${env.apiAccessKey}`
      );
      return { photos };
    } catch (error) {
      return { photos: null };
    }
  },
  data() {
    return {
      isLoading: false,
      isFullPage: true
    };
  },
  created() {
    this.loading();
  },
  methods: {
    loading() {
      this.isLoading = true;
      while (!this.photos);
      this.isLoading = false;
    }
  }
};
</script>
