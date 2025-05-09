<template>
  <client-only>
    <NavBar />
    <div id="igMain" class="ig-main"></div>
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
</script>
<style scoped></style>
<style></style>
