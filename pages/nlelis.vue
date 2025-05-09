<template>
  <div class="body">
    <section class="hero">
      <div class="hero-content">
        <div class="images-container">
          <!-- "n" Image -->
          <div class="n-image">
            <img src="/n.png" alt="n" width="95px" height="80px" />
          </div>

          <!-- Face Image -->
          <div class="face-image">
            <img src="/face.jpg" alt="face" class="face" />
          </div>

          <!-- "j" Image -->
          <div class="j-image">
            <img src="/j.png" alt="j" width="95px" height="80px" />
          </div>
        </div>

        <h1 class="title">Nietzchan Jake Lelis here. 👋</h1>

        <p class="subtitle">
          I build websites that look great, launch quickly and drive sales for
          your business.
        </p>

        <div class="footer">
          <p>Contact me. 👇</p>
          <a href="mailto:jake.lelis05@gmail.com">jake.lelis05@gmail.com</a>
        </div>
      </div>
    </section>
    <Card />
  </div>
</template>

<style scoped>
.body {
  color: whitesmoke;
  font-family: "Figtree", sans-serif;
  background-color: #080808;
  padding-bottom: 2rem;
}

.body::after {
  content: "";
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url("/noise.png");
  opacity: 0.1;
  pointer-events: none;
  z-index: 1000;
}
.hero {
  height: 90vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 1rem;
  padding-top: 5rem;
  background-image: url("/clouds.png");
  background-size: cover;
  background-position: center;
}

.hero-content {
  max-width: 64rem;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.images-container {
  position: relative;
  width: 12.5rem;
  height: 6.5rem;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 2rem;
}

.n-image {
  position: absolute;
  left: 10px;
  top: 0;
  z-index: 3;
  transform: rotate(-10deg);
}

.n-image img {
  width: 95px;
  height: 100px;
}

.face-image {
  position: relative;
  z-index: 2;
  transform: rotate(9deg);
}

.face-image img {
  width: 52px;
  height: 80px;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
  border: 4px solid white;
}

.j-image {
  position: absolute;
  right: 10px;
  bottom: 0;
  z-index: 3;
  transform: rotate(-10deg);
}

.j-image img {
  width: 95px;
  height: 100px;
}

.title {
  font-size: 2.2rem;
  font-weight: 600;
  line-height: 1.2;
  margin-bottom: 0.5rem;
}

.subtitle {
  font-size: 0.8rem;
  line-height: 1.5;
  max-width: 20rem;
  margin: 10px auto;
}

.buttons {
  display: flex;
  gap: 1rem;
  margin-top: 1.5rem;
}

@media (max-width: 640px) {
  .buttons {
    flex-direction: column;
  }
}

.btn {
  padding: 0.75rem 1.5rem;
  font-weight: 500;
  border-radius: 0.375rem;
  transition: all 0.3s ease;
  text-decoration: none;
}

.btn-primary {
  background-color: #d6b914;
  color: black;
  transition: all 0.3s;
}

.btn-primary:hover {
  background-color: #fdd700;
}

.btn-secondary {
  background-color: #333333;
  color: #a3a3a3;
  transition: all 0.3s;
}

.btn-secondary:hover {
  opacity: 0.8;
}

.footer {
  margin-top: 6rem;
  font-size: 0.875rem;
  color: #a3a3a3;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.25rem;
}

.footer a {
  color: white;
  text-decoration: none;
}
</style>

<script>
import { useSeoMeta, useHead } from "@vueuse/head";
const title = "ImpactfulGames";
const description =
  "A game catalogue with interactive features that provide detailed information on video games across a wide range of genres, inspired by the structure and functionality of platforms like MyAnimeList.";

useSeoMeta({
  title: () => title,
  description: () => description,
  charset: "utf-8",
  viewport: "width=device-width, initial-scale=1.0",
});
useHead({
  link: [
    { rel: "icon", type: "image/png", href: "/joystick.png" },
    { rel: "stylesheet", href: "/reset.css" },
    { rel: "stylesheet", href: "/custom.css" },
    { rel: "preconnect", href: "https://fonts.googleapis.com" },
    { rel: "preconnect", href: "https://fonts.gstatic.com", crossorigin: "" },
    {
      rel: "stylesheet",
      href: "https://fonts.googleapis.com/css2?family=DM+Serif+Text:ital@0;1&family=Russo+One&display=swap",
    },
    {
      rel: "stylesheet",
      href: "https://fonts.googleapis.com/css2?family=Figtree:ital,wght@0,300..900;1,300..900&display=swap",
    },
  ],
});
</script>
