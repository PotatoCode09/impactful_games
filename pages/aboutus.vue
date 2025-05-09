<template>
  <client-only>
    <NavBar />
    <div id="eiMain" class="ei-main">
      <div class="about-us-container">
        <h1>About Us</h1>
        <div class="team-members">
          <h2>Our Team</h2>
          <ul>
            <li v-for="member in team" :key="member.name">
              <p>
                <strong>{{ member.name }}</strong
                ><br />
                <span>{{ member.role }}</span
                ><br />
                <a :href="member.link">Learn more</a>
              </p>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <Copyright />
  </client-only>
</template>

<script setup lang="ts">
import { useSeoMeta, useHead } from "@vueuse/head";

const title = "Impactful Games | Home";
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
  ],
});

const team = [
  { name: "Arañez", role: "Project Lead / Software Developer" },
  { name: "Abenoja", role: "Software Developer" },
  { name: "Andrade", role: "Software Developer" },
  { name: "Lelis", role: "Software Developer" },
  { name: "Posas", role: "Software Developer" },
];
</script>

<style scoped>
.about-us-container {
  max-width: 960px;
  margin: 0 auto;
  padding: 2rem;
  font-family: "Roboto Flex", sans-serif;
  background-color: #f9f9f9;
  border-radius: 0.5rem;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.05);
}

.about-us-container h1 {
  font-family: "Teko", sans-serif;
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.team-members {
  margin-top: 2rem;
}

.team-members h2 {
  font-family: "Teko", sans-serif;
  font-size: 2rem;
  margin-bottom: 1rem;
}

.team-members ul {
  list-style-type: none;
  padding: 0;
}

.team-members li {
  margin-bottom: 1rem;
}

.team-members a {
  text-decoration: none;
  color: #007bff;
}
</style>
