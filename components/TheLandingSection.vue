<script setup lang="ts">
const navLinks = [
  {
    label: "About",
    route: { path: "/", hash: "#about" },
  },
  {
    label: "Experience",
    route: { path: "/", hash: "#experience" },
  },
  {
    label: "Projects",
    route: { path: "/", hash: "#projects" },
  },
  {
    label: "Articles",
    route: { path: "/", hash: "#articles" },
  },
];
</script>

<template>
  <div id="landing-section--container">
    <div id="landing-section--title">
      <hgroup>
        <h1>Daniel Sueakham-Silva</h1>
        <div>
          <p>
            Frontend Developer <br />
            & UI/UX Designer
          </p>
          <p>Portfolio</p>
        </div>
      </hgroup>
    </div>
    <div id="landing-section--foreground" />

    <nav>
      <NuxtLink v-for="link in navLinks" :to="link.route" class="nav-link">{{
        link.label
      }}</NuxtLink>
    </nav>
  </div>
</template>

<style lang="scss">
#landing-section--container {
  position: relative;
  height: 100vh;
  width: 100%;
  overflow: hidden;
  background-image: url("/images/Background.svg");
  background-size: cover;
  background-position: center center;

  #landing-section--foreground {
    position: absolute;
    inset: 0;
    z-index: 3;
    background-image: url("/images/Foreground.svg");
    background-size: cover;
    background-position: center center;
  }

  #landing-section--title {
    display: flex;
    flex-direction: column;
    max-width: 100%;
    padding: $page-padding;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 2;
    mix-blend-mode: overlay;
    color: $heading-text-color;
    h1 {
      font-weight: bold;
      font-size: 7.2vw;
      text-transform: uppercase;
    }
    div {
      display: flex;
      justify-content: space-between;
    }
    p {
      text-transform: uppercase;
    }
    p:last-of-type {
      font-size: 2rem;
      font-weight: bold;
    }
  }

  nav {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    position: absolute;
    bottom: $page-padding;
    left: $page-padding;
    z-index: 4;
  }
}
</style>
