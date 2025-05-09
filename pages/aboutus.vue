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
                <strong><a :href="member.link">{{ member.name }}</a></strong><br />
                <span>{{ member.role }}</span>
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
  {
    name: " John Patrick Y. Arañez",
    role: "Project Lead / Software Developer",
    link: "/jarañez",
  },
  { name: "Jaaseia Gian Abenoja", role: "Software Developer", link: "/jabenoja" },
  { name: "Jamir Oasis M. Andrade", role: "Software Developer", link: "/jandrade" },
  { name: "Nietzchan Jake Lelis", role: "Software Developer", link: "/nlelis" },
  { name: "Rico Martin Carl V. Posas", role: "Software Developer", link: "/rposas" },
];
</script>
