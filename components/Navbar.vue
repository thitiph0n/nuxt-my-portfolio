<template>
  <b-navbar>
    <template #brand>
      <b-navbar-item tag="NuxtLink" :to="{ path: '/' }">
        <p class="has-text-weight-semibold is-size-5">Thitiphon.me</p>
      </b-navbar-item>
    </template>
    <template #start>
      <b-navbar-item tag="NuxtLink" :to="{ path: '/about' }">
        About
      </b-navbar-item>
      <b-navbar-item tag="NuxtLink" :to="{ path: '/blog' }">
        Blog
      </b-navbar-item>
      <b-navbar-item tag="NuxtLink" :to="{ path: '/gallery' }">
        Gallery
      </b-navbar-item>
    </template>

    <template #end>
      <b-navbar-item tag="div">
        <div class="buttons">
          <nuxt-link to="/contact" class="button is-dark">
            <strong>Contact Me</strong>
          </nuxt-link>
        </div>
      </b-navbar-item>
    </template>
  </b-navbar>
</template>
