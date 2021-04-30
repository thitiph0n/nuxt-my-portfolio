<template>
  <div class="container">
    <h1 class="title mt-6 mb-6 has-text-centered is-size-2">About me</h1>
    <div class="columns is-7 px-5 ">
      <div class="column is-two-fifths">
        <b-image
          :src="require('@/assets/my-profile.jpg')"
          alt="my-profile"
          ratio="9to16"
          responsive
        ></b-image>
      </div>
      <div class="column p-6">
        <div class="content">
          <h1>Hi I'm Thitiphon</h1>
          <h2>Sleep😴 / Code👨‍💻 / Take a photo📸</h2>
          <p>
            I'm 3rd year student of bachelor of engineering program in Computer
            Engineering at KMUTT. Now I'm interested in Web development, Cloud
            technology, IOT, IT Infrastructure, and Blockchain technology
          </p>
          <h3>My Skills👨🏼‍💻</h3>
          <ul>
            <li>HTML&(plenty of)CSS😆</li>
            <li>JavaScript</li>
            <li>Git</li>
            <li>Docker</li>
            <li>SQL&NOSQL</li>
            <li>Node.js</li>
          </ul>
          <h3>Experienced with🧑‍🚀</h3>
          <ul>
            <li>Go</li>
            <li>Python</li>
            <li>Kubernetes</li>
            <li>React.JS</li>
            <li>Vue.JS</li>
          </ul>
          <h3>Hobby🎬</h3>
          <ul>
            <li>Watching movies</li>
            <li>Photography</li>
            <li>Cycling</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>
