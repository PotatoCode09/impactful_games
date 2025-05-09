import NavBar from '@/components/NavBar.vue';
<template>
  <client-only>
    <NavBar />
    <div id="igMain" class="ig-main"></div>
    <Copyright />
  </client-only>
</template>

<script setup lang="ts">
import { useSeoMeta, useHead } from "@vueuse/head";
const title = "Kamotech | Terms of Service";
const description =
  "Terms of Service for Kamotech, a game catalogue platform that allows users to browse, rate, comment, and interact with various video games across multiple genres.";

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

const userLevel = useCookie<number>("userLevel", {
  sameSite: "none",
  secure: true,
  maxAge: 60 * 60 * 24,
});
userLevel.value = userLevel.value ?? -1;
let navAdminMode = userLevel.value >= 2 ? "ig-nav-admin" : "";
</script>
<style scoped></style>
<style></style>
